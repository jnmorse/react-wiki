# Higher Order Components

A higher order component is basic a component that acts like a wrapper that may
add additional functionality to the component that it wraps. This is how connect
in Redux is able to inject props into a component.

The important parts is that a higher order is a function that returns a
component that will wrap another component.  The component to be wrapped is
passed in as a argument to the function.

Then we may use props as a way of connecting functionally to our component.

## Example

```javascript
export default function(ComposedComponent) {
  class Notify extends Component {
    constructor(props) {
      super(props)

      this.state = {
        options: {
          icon: 'https://raw.githubusercontent.com/jnmorse/freecodecamp-resources/master/icons/alarm.png',
          body: 'Notify'
        },
        title: '',
        error: false,
        notifier: null
      }
    }

    render() {
      return (
        <ComposedComponent
          { ...this.props }
          notify={this.sendNotification.bind(this)}
          error={this.state.error}
          setTitle={this.setTitle.bind(this)}
          setIcon={this.setIcon.bind(this)}
        />
      )
    }

    setTitle(title) {
      this.setState({ ...this.state, title })
    }

    setIcon(icon) {
      const options = { ... this.state.option, icon }

      this.setState({ ...this.state, options })
    }

    componentWillMount() {
      const notifier = new Promise((resolve, reject) => {
        const notify = function(title, options) {
          return new Notification(title, options)
        }

        if (!("Notification" in window)) {
          reject('Notifiaction not supported')
        }

        else if (Notification.permession === 'granted') {
          resolve(notify)
        }

        else if (Notification.permission !== 'denied') {
          Notification.requestPermission((permission) => {
            if (permission === 'granted') {
              resolve(notify)
            }

            else {
              reject('permission denied')
            }
          })
        }
      })

      this.setState({ notifier })
    }

    sendNotification(body, config) {
      let title = this.state.title
      let options = { ...this.state.options, body }

      if (config) {
        title = config.title || this.state.title
        options = { ...options, icon: config.icon }
      }

      this.state.notifier
        .then((notify) => notify(title, options))
        .catch((error) => this.setState({ error: {message: error} }))
    }
  }

  return Notify
}
```

## Demo

http://codepen.io/jnmorse/pen/wGyJzx
