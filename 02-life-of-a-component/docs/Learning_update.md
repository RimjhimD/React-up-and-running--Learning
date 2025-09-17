# Chapter 2: Life of a Component

## Keynotes

### Function Component
```jsx
const MyComponent = function() {
  return <span>I am so custom</span>;
};
```

### Class Component
```jsx
class MyComponent extends React.Component {
  render() {
    return <span>I am so custom</span>;
  }
}
```

### Using Props
```jsx
// Function Component
const Greeting = (props) => (
  <h1>Hello, {props.name}!</h1>
);

// Class Component
class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

### Default Props
```jsx
// Function Component with default props
const Greeting = ({ name = 'Guest' }) => (
  <h1>Hello, {name}!</h1>
);

// Class Component with default props
class Greeting extends React.Component {
  static defaultProps = {
    name: 'Guest'
  };

  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

## Key Points
- Use function components for simple, presentational components
- Use class components for complex components with state and lifecycle methods
- Props are read-only and passed down from parent to child
- Default props provide fallback values when props aren't provided
- Always include the required React scripts:
  ```html
  <script src="../react/react.js"></script>
  <script src="../react/react-dom.js"></script>
  <script src="../react/babel.js"></script>
  ```

