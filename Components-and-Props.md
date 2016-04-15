# Components and Props

Properties is one way of extending our components functionality. These props
can be any number of things. Numbers, DOM elements, components, functions,
objects or arrays.

When the component receives new props, much like if the state is changed, the
component will be slated to go though its next render cycle. This will only
happen however if new props are sent generally via another component updating
because of a state change.

If the props are passed in externally via a global variable and that external
variable is changed however the component will not update on its own without
some sorta of event notifying it that it should update.

## Children Props

There is one sorta special prop for components known as children. This prop
is usually used to define sub components, elements, or string passed into
another component.

### Example 1

```javascript
class Button extends Component {
 render() {
   return <button>some button</button>
 }
}

class Page extends Component {
 render() {
   return (
     <div>
       { this.props.children }
     </div>
   )
 }
}

ReactDOM.render(
 <Page><Button /></Page>
 , document.getElementById('app')
)
```

This is probably a pretty horrible example, but you can see that `Button` is
being passed a child element to the Page component. As a result when it is
rendered our button will be outputted between the div tags.

## General Properties

Most the time we can name properties whatever we like. There however our at
least a few exceptions. These exceptions are [ref][1], [key][2] and
[dangerouslySetInnerHTML][3]. These will not be discussed in this section.

It may be confusing if a property on a component has the same name as how you
might add a event handler to a DOM element. `onClick`, `onChange`, `onSubmit`,
etc.

### Example 2
```javascript
class form extends Component {
 render() {
   return (
     <form>
       <Button onClick={ (click) => console.log('I was clicked') }>
         click me!
       </Button>
     </form>
   )
 }
}

class Button extends Component {
 render() {
   <button onClick={this.props.onClick}>{this.props.children}</button>
 }
}
```

In this example a `onClick` handler function is being passed as a property to
the Button component, but the event is only being registered for it when it is
used on the actual DOM element. Remember that a if it starts with a capital
letter, it is a component, and if it doesn't then its referencing a DOM node.

[1]: https://facebook.github.io/react/docs/more-about-refs.html
[2]: https://facebook.github.io/react/docs/multiple-components.html#dynamic-children
[3]: https://facebook.github.io/react/tips/dangerously-set-inner-html.html
