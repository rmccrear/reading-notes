# useReduce in React

## How is an Express REST API server like a reducer?

The concept of a reducer should be familiar to all web developers because a REST API server follows the reducer pattern.

## The type "verb"

Just as a REST API server accepts an "HTTP verb" (GET, POST, PUT, or DELETE), a reducer in react expects a "type" on the payload object. In a REST API server, the POST, PUT, and DELETE verbs change state. In the context of the REST API, your state would be stored in the database on a server. Changing state in a REST API could look like this:

    axios({method: PUT}, data: {value: 2});

In the context of a react app, state would refer to the state of the UI in your browser rather than the state of the database on the server.  But, following a similar pattern, you could choose verbs such as INCREMENT or DECREMENT. 

Changing state in a react app would then look like this:

    // App.js
    ...
    dispatch({type: INCREMENT});
    ...

or

    // App.js
    ...
    dispatch({type: DECREMENT});
    ...

Just like in a REST API you need to write the code that makes changes to the state actually change. On the server, you might do this in a `routes` directory. In the case of a React app using useReducer, you can put this in a separate file called `reducers.js`

    // reducers.js
    const reducer = (state, action) {}
      if(action.type === 'INCREMENT') {
        return {
          ...state,
          count: state.count+1;
        }
      }
    }
        
Maybe you can see how this reducer pattern resembles a REST API route. The REST API route would take in different parameters than the React reducer. Another difference is that it would get and set the state with database calls within the route's function. But they are similar in that they are both taking in a "verb" and data as input, and then they are changing state on completion.

By the way, you can also send in data to reducer. Let's say you want to show how much to increment the `count`. The code would look like this:

    // App.js
    ...
    dispatch({type: INCREMENT, step: 3});
    ...

And you would also need to modify the reducer so that it increments the count by the value of 'step'. It will look like this:

    // reducers.js
    const reducer = (state, action) {}
      if(action.type === 'INCREMENT') {
        return {
          ...state,
          count: state.count + action.step; // increase by the value of 'step'
        }
      }
    }

All this is used in the React component like this:

    import reducer from './reducers'
    const App = (props) => {
      const [state, dispatch] = useReducer(reducer, {count: 0})

      const handleClick () ={
        dispatch({type: "INCREMENT", step: 3}); // send this as a message to the reducer.
      }

      return (
        <div onClick={handleClick}> // change the state of the UI.
          {state.count} // access the current value of the state of the UI.
        </div>
      )
    }


You can see that the JSX in the App.js file is pretty simple. That's good, so we let the JSX focus on rendering nicely in the UI for the user. On the other hand, a lot of the logic is isolated in the `reducers.js` file. That file also has an advantage of being testable in isolation. Writing tests is hard, so putting all the logic in one place makes it easier. Additionally, that file has no other dependencies. So there is nothing to mock. Just input messages with a `type` "verb" and output the expected state change.

Your `reducers.js` file can grow to include more more complicated state changes, and still be managed since it is full of pure functions.

[Here is a quick example of useReducer on replit.](https://replit.com/@rmccrear/ReactUseReduce)
