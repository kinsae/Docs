## INTRODUCTION TO REACT

Open Source view library created and maintained by Facebook. It's a great tool to render the User Interface (UI) of modern web applications.

## JSX - JavaScript XML

- allows us to write HTML directly in JS

  ```
  const JSX = <div>...</div>
  ```

- JSX is not a valid JS, so needs transpiler (`Babel`) to convert JSX into valid JS
- include JS in jSX using `{...}`

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
