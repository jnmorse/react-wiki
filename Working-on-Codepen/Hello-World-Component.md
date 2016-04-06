# Hello World Component

Here we will flush out our template a little more and get started on learning
React.  So you will want to open the pen we made in the previous step[1].

Go to the Codepen[2] website if your not there already, sign in if you are not
already signed in, and on the right there should be a list of your recent pens.
Open the template from the last step[1].

If you had been working on other projects and the pen is not showing there, you
will need to go to your profile, then you may need to click on public to find
your pen there.

Once your pen is open we can now get to work.

## Adding a Binding point in the HTML

The first step that will be needed is to add something to bind our components
to.  Since this is working on codepen we don't need to define a complete HTML
document since this is largely done for us.  So we will be just adding a div
with the id of app in the html pane.

You can type it out longhand;

```html
<div id="app"></div>
```

or a little secret, Codepen allows you to use emmet style shortcuts to create
the html, so you can just type `#app`, and then press tab, and it will expand
out to be the div with an id of app above.

Now for our first component and most of the content of this wiki I plan to use
es6 syntax since we are using babel and it gives us access to it, and since
I also plan to use JSX for creating HTML elements. I will try to describe what
the es6 syntax is doing as we come to it, and we will be starting with some of
it right now.

So to start with in the JavaScript pane we will add the following.

```js
const { Component } = React
const { render } = ReactDOM
```

Woah!? whats with `const` and the `{ } = React` stuff?

So first off `const` is a different way of declaring a variable, in this case we
are specifying that the variables we assign are not editable.  They have a value
and that value should only be that value.

If you assign a variable this way, `const a = 1` then later try to change that
variable, `a++`, you will get an error telling you that `a` is read-only in
console.

The second thing `const { Component } = React` is known as "destructuring
assignment". we are taking `Component`, which you'd normally have to type
`React.Component` to use, and making it, it's own thing.

So in the future whenever we need to reference `React.Component` we instead
only need to reference `Component`.

So next we will create our first component.

```
class App extends Component {
  render() {
    return <div>Hello World</div>
  }
}
```

So what we have here is we are declaring a class that is named App and that
extends `React.Component`.

It is important that the name of our React components start with a capitial
letter.  This allows the JSX converter know that when we use this component,
that is not a HTML element we are trying to render. So keep in mind that div
is return a HTML element, while App is our component.

A class is essentially a function that has certain prototype methods attached
to it, and the only required one is render.

```js
render() {
  return <div>Hello World</div>
}
```

So render is a function method attached to our App class and is required by
React.  It needs to return something, that something could be null, another
React component, or in this case what looks like an HTML element.

Its important to not confuse this with actual HTML, behind the scenes what is
actually being returned is;

```js
React.createElement(
  'div',
  null,
  'Hello World'
);
```

In our return we, much like HTML can only have one base element, so is true
with React components.  We can not for instance do this.

```js
render() {
  return (
    <h1>Hello World</h1>
    <p>My Name is Joseph</h1>
  )
}
```

This will result in an error, we can nest other elements inside the base
element, but we can not return two side by side elements.

You may have also noticed I wrapped the return in braces `()`.  This lets us
break up our return a bit more cleanly and easier for multiple lines. Earlier
I didn't since it fit nicely on a single line.

So now that our component is complete.

```javascript
const { Component } = React
const { render } = ReactDOM

class App extends Component {
  render() {
    return <div>Hello World</div>
  }
}
```

we now need a way to "mount" it to the HTML DOM. to do this we will use the
the render method from ReactDOM. It wasn't really nessary, but I also set
constant much like I did with Component for the `ReactDOM.render` method so I
only have to call it `render`.

The ReactDOM render method takes two arguments, the component we are mounting,
and where we are mounting it. So are completed component app looks like this
now.

```javascript
const { Component } = React
const { render } = ReactDOM

class App extends Component {
  render() {
    return <div>Hello World</div>
  }
}

render(
  <App />
  , document.querySelector('#app')
)
```

You should notice that App corresponds with our App component and its being
used much like a self terminating tag in HTML.  The `/>` at the end is required in
this case, where as it is optional in HTML 5.

Now that is done, and you click run if you disabled the Auto Update, you should
see "Hello World" in your pen preview pane.

Save your changes.

**Note**: I've sometimes had to open a pen a second time, select the template
box again then save one more time in order for Codepen to remember this is a
template.

[1]: setting-up-a-template-on-codepen.md (Setting up a Template on Codepen)
[2]: http://codepen.io/ (Codepen)
