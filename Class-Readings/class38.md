# React II

## Conditional Rendering

You can render some components, depending on state.

Using normal `if()` logic:


    function Greet(props) {
    cont loggedIn = props.loggedIn
    if(loggedIN)
        return <Greeting />
    return <Greeting />
    }

You can also use stateful components, where the state is stored in the component rather than the props. Or using inline logical operators. Really any valid JS can work.

You can also return Null from a component to prevent it from rendering, however it's lifecycle methods will still be called.

## Lists and Keys

You render lists of JSX components, though typically you'd render lists inside of a single component. When rending multiple items inside of a component, a key will need to be assigned to items in the list. These keys should be unique at the sibling level, and by default are the index values of the items. However, if a list's order will change you should avoid using index values. Keys should also be assigned at the parent level, rather than the individual item level.

## Forms

Because forms in HTML can keep their own internal state, React has to handle them a bit differently. We can make it so that React become the single source of truth for forms, this is called controlled components.

We can set up event listeners so that when fields on a form are changed, then react can set state within the reactDOM.

`<input>` field normally defines its text by its children, but in react text is defined by a value attribute.

`<select>` tag can define multiple `<option>` tags, and set one of those options to default by also associating a selected attribute with an option. In React, we instead assign the selected option to a value attribute on the root `<select>` tag.

## Lifting State

When multiple components need access to the same state, in essence sharing their state together, then we can lift that state up to the most direct common ancestor of both components. This way that ancestor can become a single source of truth.

## Composition

When a component may have an unknown number of children, you should pass them as props.

You can also set up a generic component that a more specialized component can configure and render.

## Inheritance

>At Facebook, we use React in thousands of components, and we haven’t found any use cases where we would recommend creating component inheritance hierarchies.

>Props and composition give you all the flexibility you need to customize a component’s look and behavior in an explicit and safe way. Remember that components may accept arbitrary props, including primitive values, React elements, or functions.

>If you want to reuse non-UI functionality between components, we suggest extracting it into a separate JavaScript module. The components may import it and use that function, object, or a class, without extending it.