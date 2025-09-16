# Hello World in React

## Learning Objectives
- Set up a basic React environment
- Render a simple component using React
- Understand JSX syntax

## Setting Up React

### Using CDN (For Simple Projects)
Include these scripts in your HTML file:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Hello React</title>
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
</head>
<body>
    <div id="root"></div>
    
    <script type="text/babel">
        // Your React code will go here
    </script>
</body>
</html>
```

## Understanding JSX

JSX is a syntax extension that allows you to write HTML-like code in your JavaScript:

```jsx
const element = <h1>Hello, world!</h1>;
```

## Rendering in React

To display content using React, you'll use `ReactDOM.createRoot()` and the `render` method:

```jsx
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<h1>Hello, world!</h1>);
```

## Creating Your First Component

### Function Component Example

```jsx
function HelloWorld() {
    return <h1>Hello World!</h1>;
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<HelloWorld />);
```

Or using arrow function syntax:

```jsx
const HelloWorld = () => <h1>Hello World!</h1>;

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<HelloWorld />);
```

## Key Takeaways

- React uses **components** to build user interfaces
- **JSX** allows you to write HTML-like code in JavaScript
- `ReactDOM.createRoot().render()` is used to render React elements to the DOM
- The simplest React app renders a single component
- Changes in JSX are automatically reflected in the browser

## Example: Complete Hello World App

```html
<!DOCTYPE html>
<html>
<head>
    <title>My First React App</title>
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
</head>
<body>
    <div id="root"></div>
    
    <script type="text/babel">
        // Define a component
        function App() {
            return (
                <div>
                    <h1>Welcome to React!</h1>
                    <p>This is your first React component.</p>
                </div>
            );
        }

        // Render the component to the DOM
        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(<App />);
    </script>
</body>
</html>
```

## Next Steps

- Try modifying the JSX in the example
- Add more components to your app
- Learn about props and state in React
- Consider using Create React App for larger projects
- Include React and ReactDOM via CDN (for simple projects):
```html
<script src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
Create a root element in HTML:

html

<div id="root"></div>
### 2. JSX
JSX is a syntax extension that looks like HTML but is written in JavaScript.

Example:

js
Copy code
const element = <h1>Hello, world!</h1>;
3. Rendering in React
Use ReactDOM.createRoot and render to display content:

js
Copy code
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<h1>Hello, world!</h1>);
4. Creating a Simple Component
Function Component Example:

js

const Hello = () => <h2>Hello from a React component!</h2>;
root.render(<Hello />);
5. Takeaways
React uses components to render UI.

JSX allows writing HTML-like code in JavaScript.

ReactDOM.render (or createRoot().render) is used to render React elements on the page.

The simplest React app is just a “Hello World” component.

Example Worked On
Rendered a simple HelloWorld message:

js

const HelloWorld = () => <h1>Hello World!</h1>;
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<HelloWorld />);
Observed how changing the JSX updates the browser view instantly.

