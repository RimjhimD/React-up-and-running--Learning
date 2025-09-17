# Chapter 1: Hello World in React

## Things to Remember
- React uses a virtual DOM for efficient updates
- Components are the building blocks of React applications
- JSX is not HTML but gets compiled to JavaScript
- Always include Babel for JSX transformation in the browser

## Keynotes

### Basic React Setup
```html
<script src="../react/react.js"></script>
<script src="../react/react-dom.js"></script>
<script src="../react/babel.js"></script> <!-- Required for JSX -->
```

### React without JSX
```javascript
// Creating elements with React.createElement
ReactDOM.render(
  React.createElement(
    'h1',
    { id: 'my-heading' },
    React.createElement('span', null, 'Hello'),
    ' world!'
  ),
  document.getElementById('app')
);
```

### Nested Elements
```javascript
ReactDOM.render(
  React.createElement(
    'h1',
    { id: 'my-heading' },
    React.createElement(
      'span',
      null,
      'Hello ',
      React.createElement('em', null, 'World')
    ),
    '!'
  ),
  document.getElementById('app')
);
```

### JSX Version
```jsx
ReactDOM.render(
  <h1 id="my-heading">
    <span>Hello <em>JSX</em></span> world!
  </h1>,
  document.getElementById('app')
);
```

## Key Differences to Note
1. **JSX vs createElement**
   - JSX is more readable and similar to HTML
   - createElement is more verbose but doesn't require transpilation

2. **Nesting**
   - JSX makes nested structures cleaner
   - createElement requires explicit nesting of function calls

3. **Performance**
   - Both approaches compile to the same JavaScript
   - JSX is transformed into createElement calls during build

