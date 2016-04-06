## Setting up a Template on Codepen

If you haven't already done so, you should create an account on [Codepen][1].
All you need is the free account, but if you wish to sign up for a paid account
the choice is yours.

Once You have done that you will want to click the New Pen button located in the top right of the screen.

![Create New Pen][figure 1]

[figure 1][figure 1]

Now You should see a new pen opened like this.

![New Pen][figure 2]

[figure 2][figure 2]

## Adding React to the Template

Now to add React to your project unfortunately is currently not as straight
forward as it is to add something like jQuery.  You can add certain libraries
by just typing there name or selecting them from a drop down.  For React though
we will need to add two libraries.  And we will want the non-minified,
non-production versions.

So the URLs we are going to want to use can be found [here][2].

![Open Settings][figure 3]

[figure 3][figure 3]

So to add them you will first want to either click the settings button, or the
little cog icon under JS. If you got there by clicking settings, you can switch
to the JavaScript settings by clicking on "JavaScript".

Once there you will want to select Babel from the JavaScript Preprocessors drop
down list.

Then under "Add External JavaScript" you will want to add these two urls.

https://cdnjs.cloudflare.com/ajax/libs/react/0.14.8/react.js

https://cdnjs.cloudflare.com/ajax/libs/react/0.14.8/react-dom.js

Once those are set, click CSS and select the CSS Preprocessor SCSS.  You could
choose Sass if you prefer, but I will be using the SCSS version of Sass.

To give and short example in the difference

SCSS would be like this;
```scss
#app {
  background-color: green;

  h1 {
    color: red;
  }
}
```

While Sass is like this
```sass
#app
  background-color: green
  h1
    color: red
```

It can be a little confusing since both SCSS and SASS are just two different
syntaxes that Sass uses.

If you would also like to use a HTML preproccessor you may, but is very little
reason to with react.

Give you pen a title like "react starter", and make sure to check the template
box, and click save & close.

Don't worry about adding any additional content at this time.  Our template
largely ready to be used.

We will add some initial content to our template in the section,
"[Hello World Component][3]"

### Optional

Under Behavior I like to un-check the "Auto Update Preview" option.  This makes
it so you either have to click the run button that will be added or press
`cntrl+shift+5` to refresh your pen changes.

[1]: https://codepen.io/signup (Code Pen Signup)
[2]: https://cdnjs.com/libraries/react/ (React CDN)
[3]: ../README.md

[figure 1]: images/create-new-pen.png (Create New Pen)
[figure 2]: images/new-pen.png (New Pen Window)
[figure 3]: images/open-settings.png (Open The Settings Pane)
