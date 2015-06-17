# ReactTutorial

Running through [React tutorial](http://blog.risingstack.com/the-react-way-getting-started-tutorial/).
Original code on [GitHub](https://github.com/RisingStack/react-way-getting-started).

# 1. Getting Started with the React.js Tutorial

React.js is not a framework.

React.js is the "View" in the application. In a React application, you should break down your site, page or feature
into smaller pieces of components. You can also reuse it somewhere else later.

React is mainly a concept and a library just secondly.

## The Virtual DOM concept in a nutshell

React's diffing algorithm uses the tree representation of the DOM and re-calculates all subtrees when it's parent got
modified (marked as dirty).

## Component-driven development

In the component-driven development, you won't see the whole site in one template. It makes things easier to understand,
to maintain and to cover with tests.

### What should a component contain?

It's wise to follow the [single responsibility principle](http://snip.ly/r3c4#http://en.wikipedia.org/wiki/Single_responsibility_principle)
and ideally, design your components to be responsible for only one thing.

Your components can use other components as well.

ES5:

```javascript
var HelloComponent = React.createClass({
    render: function() {
        return <div>Hello {this.props.name}</div>;
    }
});
```

ES6:

```javascript
class HelloComponent extends React.createClass({
    render() {
        return <div>Hello {this.props.name}</div>;
    }
});
```

#### JSX

The same code above can be written in pure JS:

```javascript
render() {
    return React.createElement("div", null, "Hello ", this.props.name);
}
```

[HTML Tags vs. React Components](http://snip.ly/7DTB#https://facebook.github.io/react/docs/jsx-in-depth.html#html-tags-vs.-react-components)

##### Useful links

* [JSX in Depth](https://facebook.github.io/react/docs/jsx-in-depth.html)
* [JSX online compiler](https://facebook.github.io/react/jsx-compiler.html)
* [Babel: How to use the react transformer](http://babeljs.io/docs/advanced/transformers/other/react/)

We can pass properties to our components when we are building our component hierarchy. `{this.props.name}` Like
`<MyComponent name="John Doe" />`

## Bundling with Webpack and Babel

* Node.js
* npm
* debug
* superagent
* Webpack or Browserify
* Babel: JSX & ES6 => JS ES5
* [Jest](https://facebook.github.io/jest/) - testing


ES5:

```javascript
var React = require('react/addons');

class MyComponent extends React.Component{...}

module.exports = MyComponent;
```

ES6:

```javascript
import React from 'react/addons';

class MyComponent extends React.Component{...}

export default MyComponent;
```

Webpack is configuration-oriented

```
$ npm init
$ npm install --save-dev webpack
$ npm install --save-dev babel
$ npm install --save-dev babel-loader
```

