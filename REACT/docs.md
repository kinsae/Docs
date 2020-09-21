## INTRODUCTION TO REACT

Open Source view library created and maintained by Facebook. It's a great tool to render the User Interface (UI) of modern web applications.

## JSX - JavaScript XML/Extension

- allows us to write HTML directly in JS

  ```
  const JSX = <div>...</div>
  // OR
  const JSX = ( <div>...</div> );
  ```

- JSX is not a valid JS, so needs transpiler (`Babel`) to convert JSX into valid JS
- JSX elements are converted into React elements

  ```
  const jsx = <h1>hello</h1>

  // converted as React element
  const jsx = React.createElement('h1','hello');
  ```

- include JS in JSX using `{...}`

  ```
  const JSX = <div>
                { alert("JS from  JSX") }
                { /* This is a comment in JSX */ }
              </div>
  ```

- JSX must return single JSX element only. Other elements are wrapped within a single wrapper element. Having multiple return will be not transpile.

  ```
  // Valid JSX
  const JSX = <div>
                <h1>heading1</h1>
                <p>This is a paragraph</p>
              </div>

  // Invalid JSX
  const JSX = <div><h1>heading1</h1></div>
              <p>This is a paragraph</p>
  ```

- JSX tags are similar to HTML tag but strictly requires all tags to be closed.

  ```
  // examples

  <div>...</div>  // opening-closing tag
  <div />          // self-closing tag. Also used for including components
  <br />
  ```

- Rendering React element/component to the DOM using React API `ReactDOM`'s `render()` method

  ```
  // Syntax
  ReactDOM.render(componentToRender, targetNode);

  // In JSX
  const JSX = <div>
                <h1>heading1</h1>
                <p>This is a paragraph</p>
              </div>

  ReactDOM.render(JSX, document.getElementBYId('container'));

  // In HTML
  <body>
    <div id="container"></div>
  </body>
  ```

## REACT Component

1. Functional Component

- stateless component
- returns JSX or null
- function name must start with Capital letter

```
const ComponentName = function(){
  return (
    <div>hello</div>
  );
}
```

2. Class Component

- extends React.Component
- has local state and lifecycle hooks from React.Component
- uses render() method and return() in it

```
class ComponentName extends React.Component{
  constructor(props){
    super(props);
  }

  render(){
    return(
      <div>Hello</div>
    );
  }
}
```
