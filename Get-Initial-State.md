## getInitalState

When the component is initially called for this will set up the initial state of
our component. This is generally the best time to set our default values.

Please note that getInitialState is not actually a method on es6 classes.  This
is one of the differences between and es6 class component and
`React.createClass()`.

Instead we define the initial state inside the constructor method, and we must
call super here as well, passing whatever props are components constructor
method was called with.

Generally I use this time to set the most basic values that I'll expect these
to hold.  For instance `[]` for arrays, `''` for strings, and `0` for numbers.

For instance if we are building a recipe app, which is one of the
[Free Code Camp](https://www.freecodecamp.com) projects.

```JavaScript
class ExampleComponent extends Component {
  constructor(props) {
    super(props)

    this.state = {
      recipes: []
    }
  }
}
```

```JavaScript
var Component = React.createClass({
  getInitalState: function() {
    return {
      recipes: []
    }
  },
  render: function() {
    // Return something
  }
})
```
