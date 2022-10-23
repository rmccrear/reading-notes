# React useEffect hook

The `useEffect` hook is used for side effects in React function based components. In React class based components, you can use the lifecycle function like `componentDidMount` to run side effects as a place to run these. But since function based components don't have methods, we need to use `useEffect`.

In this component (see the useState intro (here)[./21-react-use-state.md])

    import React, {Fragment, useState, useEffect} from 'react';
    
    function MoreEmoji(props) {
      const [counter, setCounter] = useState(1);
    
      let emojis = [];
      for(let i=0; i<counter; i++){
        emojis.push(props.emoji)
      }
    
      // This will be called whenever the Component is rendered.
      useEffect(()=>{
        document.title = emojis.join('');
        console.log(
          `From useEffect without dependency: ${emojis.join('')}`
        )
      })
    
      return (
        <div>
          {emojis.map((emoji, i) => <span key={i}>{emoji}</span>)}
          <button onClick={()=>setCounter(counter+1)}>More</button>
          <button onClick={()=>setCounter(0)}>Reset</button>
        </div>
      )
    }

You can try the replit [here](https://replit.com/@rmccrear/MoreEmoji)

We see that `useEffect` will set the title of the HTML page to the emoji. It will just do this whenever the component renders or re-renders. If we want it to run every time the counter changes, we can by adding it to the dependency list:


      // run when the counter changes
      useEffect(()=>{
        document.title = emojis.map((e)=>e).join('');
      }, [counter])
  
  This will update the title of the page to however many emojis are set by the counter.

  We can also set it to only call the function after the component mounts. If we set the dependency list to an empty list, it will only run once over its lifecycle.

      // run only once
      useEffect(()=>{
        document.title = `Hello ${props.emoji}`
      }, [])

You can also run a function on unmount by returning a function.

      // run only once
      useEffect(()=>{
        document.title = `Hello ${props.emoji}`;
        // run on unmount
        return () => {
          document.title = `Goodbye ${props.emoji}`;
        }
      }, [])

The function called on unmount can cleanup. For example, they can unsubscribe to an API so the subscribers do not become zombies.