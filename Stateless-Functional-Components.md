# Functional Components

Another type of component that you can use in react is known as a stateless functional component.  These components will have no state, but may make use of props. An example component that you might use as a stateless functional component would be something like a general header.

```javascript
function Header(props) {
  const { title, subtitle } = props

  return (
    <header>
      <h1>{title}</h1>
      <p>{subtitle}</p>
    </header>
  )
}
```

