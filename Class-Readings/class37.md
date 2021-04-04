# React 1

ES6 Syntax and Feature Overview

### React - Hello World

        ReactDOM.render(
          <h1>Hello, world!</h1>,
          document.getElementById('root')
        );

### React - JSX

    const name = 'Josh Perez';
    const element = <h1>Hello, {name}</h1>;

    ReactDOM.render(
      element,
      document.getElementById('root')
    );

Since JSX is closer to JavaScript than to HTML, React DOM uses camelCase property naming convention instead of HTML attribute names.

These two examples are identical:

    const element = (
      <h1 className="greeting">
        Hello, world!
      </h1>
    );

    const element = React.createElement(
      'h1',
      {className: 'greeting'},
      'Hello, world!'
    );

React.createElement() performs a few checks to help you write bug-free code but essentially it creates an object like this:

    // Note: this structure is simplified
    const element = {
      type: 'h1',
      props: {
        className: 'greeting',
        children: 'Hello, world!'
      }
    };

When React sees an element representing a user-defined component, it passes JSX attributes and children to this component as a single object. We call this object “props”.

    function Welcome(props) {
      return <h1>Hello, {props.name}</h1>;
    }

    const element = <Welcome name="Sara" />;
    ReactDOM.render(
      element,
      document.getElementById('root')
    );

- We call ReactDOM.render() with the <h1>Welcome name="Sara" </h1> element
- React calls the Welcome component with {name: 'Sara'} as the props
- Our Welcome component returns a Hello, Sara</ element as the result
- React DOM efficiently updates the DOM to match <h1>Hello, Sara</h1>

## References

[React - Installation]

React - Comprehensive Guide

Understanding Variables, Scope, and Hoisting in JavaScript