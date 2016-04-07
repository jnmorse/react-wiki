# Stateless Functional Components

Another type of component that you can use in React is known as a stateless
functional component.  These components will have no state, or lifecycle
methods but may make use of props.

An example component that you might use as a stateless functional component
would be something like a general header.

```javascript
const { PropTypes } = React

function Header(props) {
  const { title, subtitle } = props

  return (
    <header>
      <h1>{title}</h1>
      { subtitle ? <p>subtitle</p> : null}
    </header>
  )
}

Header.propTypes = {
  title: PropTypes.string.isRequired
}
```

## When to use

This component type probably should be generally the type you would use most
often, and should be used anytime a component will have no need for its own
state or additional methods.
