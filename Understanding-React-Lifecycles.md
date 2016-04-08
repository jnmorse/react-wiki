# Understanding React Lifecyles

React will make use of a number of methods on a class component that will be
called automatically during certain points of a components lifecycle.

Some of these lifecycles are only called once at certain stages from when your
component is first and some of them may be called upon multiple times as the
state and/or props of the component changes.  And only the render method is
required to be on your component.

The methods that happen only 'once' may be misleading a bit since it is possible
that these methods may in fact be called more then one single time, the only
refers to the instance of this component existing in our output that the once
here implies.

If a component is unmount and then mounted again later, the lifecycles will be
called again.

## Difference Between Mounted and Unmounted Components

A mounted component is a component that is currently active and in use. While
an unmounted component exist but at this current point in time is not being
utilized.

For instance take this example.

```JavaScript
const { Component } = React
const { render } = ReactDOM

class ErrorNotify extends Component {
  constructor(props) {
    super(props)

    this.state {
      error: false,
      message: ''
    }
  }

  componentWillRecieveProps(state) {
    this.setState({ state })
  }

  render() {
    if (state.error) {
      return <Message text={this.state.message} />
    } else {
      return null
    }
  }
}

render(
  <ErrorNotify />
  , document.getElementById('app')
)
```

In this example, imaging ErrorNotify is being used as a child of another
component, and its purpose is to display an error message if there is an error.


The following are the various lifecycle methods, in rough order that they take
place, and some use cases for the method.

```javascript
const { Component } = React

class ExampleComponent extends Component {
  constructor(props) {
    super(props)

    this.state = {
      example: true
    }
  }

  // These Methods only happen once
  componentWillMount() {}
  componentDidMount() {}
}

```

## componentWillMount
