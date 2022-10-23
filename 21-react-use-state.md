# React useState

React Components can be written as classes with a `render` method or as function that return as a JSX template. In React, classes can be created to keep track of state using `this.state` and `this.setState`. But hooks can be used to keep track of state in function based Components.

In React, hooks provide a sort of magical state keeping that works behind the scenes so you don't have to think about it. Each function based Component can be provided with its own state using the `useState` method. React will keep track of changes that use make to the state and re-run the function with the changes in state being inserted with the `useState` method. One part of the magic formula is that you can't use `useState` in a conditional. It should run each and every time the function runs, or it may confuse the mechanism React uses to keep track of changes.

The `useState` syntax works like this:

    function MoreEmoji(props) {
      const [counter, setCounter] = useState(0);

      let emojis = [];
      for(let i=0; i<counter; i++)
        emojis.push(props.emoji)

      return (
        <>
          {emojis.map((emoji, i) => <span key={i}>{emoji}</span>)}
          <button onClick=()=>setCounter(counter+1)>More</span>
          <button onClick=()=>setCounter(0)>Reset</span>
        </>
      )
    }

This Component will add an emoji character every time the More button is clicked. It will reset the counter to 0 if the Reset button is clicked.

The useState method will take the default state in as an argument. It will return an array with exactly two elements. The first is the previous state, the second is a function that will tell the React engine to update the state and trigger a re-render. So, we can destructure them with a convenient one liner.

Hooks are an innovation that makes function based Components just as powerful as class based components. It avoids the need for higher order Components (HOC) and render props. This can simplify things considerably. They also make it easier for the React compiler to optimize code. So, the React ecosystem is moving to function based Components. But class based Components are still supported.

