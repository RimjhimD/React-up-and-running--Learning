# Life of a React Component

## Learning Objectives
- Create function components in React
- Create class components in React
- Understand and use props in components
- Implement default props for function components
- See the difference between function and class components

## Table of Contents
1. [Function Components](#1-function-components)
2. [Class Components](#2-class-components)
3. [Using Props](#3-using-props)
4. [Default Props](#4-default-props)
5. [Component Lifecycle](#5-component-lifecycle)
6. [Best Practices](#6-best-practices)

## 1. Function Components

Function components are the simplest way to define a React component. They are JavaScript functions that return React elements.

### Basic Syntax

```jsx
const MyComponent = function() {
  return <span>I am so custom</span>;
};
```

### Usage in Render

```jsx
// To render the component:
ReactDOM.render(<MyComponent />, document.getElementById('app'));
```

### Key Points
- Simple and concise syntax
- Primarily used for presentational components
- Cannot use state or lifecycle methods (without Hooks)
- Receives props as the first parameter

## 2. Class Components

Class components are defined using ES6 classes and extend `React.Component`.

### Basic Syntax

```jsx
class MyComponent extends React.Component {
  render() {
    return <span>I am so custom</span>;
  }
}
```

### Usage in Render

```jsx
// To render the component:
ReactDOM.render(<MyComponent />, document.getElementById('app'));
```

### Key Features
- Must include a `render()` method
- Can maintain their own state
- Have access to lifecycle methods
- Access props via `this.props`

## 3. Using Props

Props (short for properties) allow components to receive data from their parent component.

### Passing and Using Props

```jsx
// Parent Component
ReactDOM.render(
  <MyComponent name="Bob" />,
  document.getElementById('app')
);

// Child Component (Class)
class MyComponent extends React.Component {
  render() {
    return <span>My name is <em>{this.props.name}</em></span>;
  }
}

// Child Component (Function)
const MyComponent = function(props) {
  return <span>My name is <em>{props.name}</em></span>;
};
```

### Accessing Props
- In class components: `this.props.propName`
- In function components: `props.propName` or destructured in parameters

## 4. Default Props

You can define default values for props using `defaultProps`.

### For Function Components

```jsx
const MyComponent = function({ name, job }) {
  return <span>My name is <em>{name}</em>, the {job}</span>;
};

MyComponent.defaultProps = {
  job: 'engineer',
};
```

### For Class Components

```jsx
class MyComponent extends React.Component {
  static defaultProps = {
    job: 'engineer'
  };
  
  render() {
    return <span>My name is <em>{this.props.name}</em>, the {this.props.job}</span>;
  }
}
```

### Key Points
- Default props are used when a prop is not provided
- Can be defined using `defaultProps` static property
- In function components, can also use default parameters

## 5. Component Setup Requirements

### Required Imports
```html
<script src="https://unpkg.com/react@17/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js">
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
```

### HTML Structure
```html
<div id="app"></div>

<script type="text/babel">
  // Your React code goes here
</script>
```

### Rendering Components
```jsx
// For a single component
ReactDOM.render(<ComponentName />, document.getElementById('app'));

// For multiple components
ReactDOM.render(
  <div>
    <Component1 />
    <Component2 />
  </div>,
  document.getElementById('app')
);
```

## 6. Best Practices

1. **Use descriptive component names** (PascalCase)
2. **Keep components focused** on a single responsibility
3. **Use default props** for optional props
4. **Keep your JSX clean** by breaking down complex components
5. **Use proper indentation** for nested JSX
6. **Comment your code** to explain complex logic
7. **Use self-closing tags** for components without children
8. **Keep your component files organized** with related components together

## Complete Examples

### Function Component with Props
```jsx
const Greeting = function({ name, role = 'user' }) {
  return (
    <div>
      <h2>Welcome, {name}!</h2>
      <p>You are logged in as: {role}</p>
    </div>
  );
};
```

### Class Component with Props
```jsx
class Greeting extends React.Component {
  static defaultProps = {
    role: 'user'
  };

  render() {
    return (
      <div>
        <h2>Welcome, {this.props.name}!</h2>
        <p>You are logged in as: {this.props.role}</p>
      </div>
    );
  }
}
```

## Next Steps

1. Try creating more complex components by combining these concepts
2. Experiment with passing different types of props (strings, numbers, arrays, objects)
3. Practice using both function and class components to understand their differences
4. Explore React Developer Tools to inspect components and props
5. Learn about React Hooks for state management in function components
