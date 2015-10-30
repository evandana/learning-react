# About ReactJS
Content copied and summarized from [Scotch.io's ReactJS Getting Started Guide](https://scotch.io/tutorials/learning-react-getting-started-and-concepts)

## Overview
 - [https://blog.risingstack.com/the-react-way-getting-started-tutorial]

## Efficient modification of virtual DOM
 - Runs a reconciliation method that updates the virtual DOM (which can be output by the Server as a React View)

 ## Components
 ```javascript
    {
        state: {},
        props: {}
    }
 ```
 - Script blocks that call `React.render( <<XML>>, <<DOM Element>> )`;
 - Also create through JS
 ```javascript
    // create
    var MyComponent = React.createClass({
        render: function(){
            return (
                <h1>Hello, world!</h1>
            );
        }
    });

    // render
    React.render(
        <MyComponent/>,
        document.getElementById('myDiv')
    );
```
 # Props
 ```javascript
    var MyComponent = React.createClass({
        render: function(){
            return (
                <h1>Hello, {this.props.name}!</h1>
            );
        }
    });

    React.render(<MyComponent name="Handsome" />, document.getElementById('myDiv'));
 ```
 # State
 - set with `getInitialState` in constructor
 ```javascript
    var MyComponent = React.createClass({
        getInitialState: function () {},
        render: function () {...}
    });
 ```
 # Events
 - attach to components as a property
 ```javascript
    // in object definiton
    incrementCount: function () {}
    // in render function
    onClick={this.incrementCount}
 ```

## JSX
 - XML (HTML-ish)
 - `class` becomes `className`
 - `for` becomes `htmlFor`
 - Use `/** @jsx React.DOM */` right after `<script ...>` so it knows to transform the markup

# Lifecycle
 - componentWillMount (pre-render, client and server)
 - componentDidMount (post-render, invoked once, only on client)
 - shouldComponentUpdate (a true return value will result in an update)
 - componetWillUnmount (pre-unload)

# Specs
 - getInitialState
 - getDefaultProps
 - mixins (array of mixins)
