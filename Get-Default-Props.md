## getDefaultProps and Constructor continued

This is another state that differs depending if we are using es6 or
`React.createClass()`.

We can use this oppertunity to define the default values of optional props that
may or may not be passed to our component.

Say we have a submit button component and the we have and optional text property
that sets what text will be displayed on the button.

```JavaScript
class SubmitButton extends Component {
  render() {
    return <button type="submit">{this.props.text}</button>
  }
}

SubmitButton.defaultProps = {
  text: 'Submit'
}
```

```JavaScript
```
