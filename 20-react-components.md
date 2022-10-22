# React components

A React app is built from Components. The React Components can manage state and respond to events like user input. The Components work together through composition rather than inheritance. A Component will have other components as children. At the bottom, they are composed of HTML Elements which are displayed on the screen. The events that are emitted from these children can be listened for in React Components and acted on.

The design of a React program is hierarchical. Each part of the UI in React can be responsible for its part, and then pass data or events that are not its responsibility up to another, more general component.
React allows the programmer to let each Component be single-purpose. If an event is associated with data only important to that Component, then the Component can maintain that state by itself. If the data or event is more general, that state can be managed by a Component higher up. This is one reason why there is a distinction between `state` and `props` in React. `state` is for data handled by that Component. `props` are managed by a parent component. Function can be passed as `props` to allow for an event in the Component to be manged by a listener in a parent component.

# JSX

JSX is React's templating language. It is very powerful because it allows you to use javascript expressions with its {}. This means anything, including other React Components can be embedded in JSX. React will automatically htmlEncode string passed to it to render. For example, when this JSX is passed,

    <div>
      {`<span>hello</span>`}
    </div>

it will render something like

    &lt;span&gt;hello&lt;/span&gt;

unless you pass it with 

    const html = `<span style='color:green'>hello</span>`;
    <div dangerouslySetInnerHTML={__html: html}>
    </div>

This will render

<span style='color:green'>hello</span>

Then it will allow the html that you set to be rendered as Html Elements. This introduces security holes if your html contains user generated data.

# Rendering

    const root = ReactDOM.createRoot(
      document.getElementById('root')
    );
    const element = <h1>Hello, world</h1>;
    root.render(element);

The `render` method of React is how react can be fast while also staying up-to-date. The React Component can pass a JSX template to `render` to be rendered into the browser. Usually this JSX will not change, or will only change in a small way. For example, if you have clock that looks like this:

    const date = new Date();
    const element = <h1>
        <span>The time is</span>
        <span>{d.getHours()}</span>
        <span>{d.getMinutes()}</span>
        <span>{d.getSeconds()}</span>
      </h1>
    render(element);

the `element` will usually only change by seconds. But in React, the whole `element` variable will be passed in to React to update. The rendering engine will not immediately update the page, but will instead render the page internally and compare it to the last time it rendered. Then, the rendering engine will only change the part of the page that needs to be updated. In this case, just the `span` with the seconds.

You can get the best of both worlds. On one hand, the Component updates freshly each time there is a change in data. You don't have to keep track of which changes happen. When you pass the changed JSX to `render`, it will efficiently update only the parts of the page that need it.

Not only does React track the changes for you, it also tracks when the changes need to happen. This is done with `state` and `setState`. When `setState` is called, the `render` method is called again and a fresh JSX template is returned from render with the newly updated state. This would mean the page would have to re-render from scratch if not for React's ability compare the fresh version with the last rendered version. In this case, React compares the new and old versions and selectively updates only the section in the page that needs changing.