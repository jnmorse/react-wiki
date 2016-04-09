## Difference Between Mounted and Unmounted

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

The Message component will only be mounted when its needed.  As such the
lifecycle states, such as `componentWillMount`, `componentDidMount` will be
called when the component is being mounted, and `componentWillUnmount` will be
called whenever the state error is set back to a false value and just before
the unmount happens.

You may see a more interactive example at this [pen][1].

[1]: http://codepen.io/jnmorse/pen/zqpPbx (Mounted and Unmounted Components)
