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

## List of Lifecyles

1. componentWillMount
2. componentDidMount
3. componentWillRecieveProps
4. shouldComponentUpdate
5. componentWillUpdate
6. componentDidUpdate
7. componentWillUnmount

## Additonal Component Specs

1. [getInitalState](Get-Intial-State)
1. [getDefaultProps](Get-Default-Props)

## Other Resources on Lifecycles

1. [Official Documentation: Component Specs and Lifecycle][1]

[1]: https://facebook.github.io/react/docs/component-specs.html
