<!-- MarkdownTOC -->

- Intro
	- Michael Jackson
	- Ryan Florence
	- Why React
	- Stocks VS. Flows
- ES6
	- Import
	- Fat arrow functions
	- Import
	- Restructuring
- React Basics
	- Events
	- React.render()
	- State
	- Components
- Career Growth
	- Exciting things to focus on
- Tools
- General Tips
	- To fix `sudo npm install`

<!-- /MarkdownTOC -->
[./react-fundamentals](local react-fundamentals folder)

# Intro

## Michael Jackson
 - Father
 - MooTools, Twitter Ads platform

## Ryan Florence
 - From Boston
 - CanvasLMS, Blackboard, EmberJS

## Why React
 - Quicker to deliver code
 - More likely to write unit tests
 - Netflix uses ReactJS
 - Problems it solves
 	- Imerative jQuery: timing dependencies and who breaks down what, when
 	- BackboneJS: thinking about time, setting up instances
 	- AngularJS
 		- fixes many issues but creates others (declarative templates)
 		- hard to find out where vars/functions originate
 		- global directives that can overwrite others (namespace hell)
 		- observes data, but totally recreates dom if new object found
 		- 
 	- EmberJS
 - Requires only knowledge of JS and a bit of JSX (but more obvious)
 	- Encourages learning JS

## Stocks VS. Flows
 - Stocks: current value ($5)
 - Flows: rate of change (5mph)
 	- Must experience it to understand it (add time)
 	- Quote from Djikstra on dynamic process

# ES6

## Import

## Fat arrow functions

## Import

## Restructuring
 - var { select, option } = React.DOM // grabs those two props from React.DOM and sets the two vars to those values

# React Basics

## Events
 - Not global
 - Handler defined in the component

## React.render()

## State
 - Use a `state` object for tracking it
 ```javascript
 	var state = {
 		isOpen: false
 	};
 ```

## Components
 - Created with `React.createClass({})`
 - methods
 	- `setState`
 	- `getInitialState`
 	- `render`
 - props
 	- `this.props.propName`
 	- `this.props.children`
 	- children can be other components
 ```javascript
 	React.render(<ComponentName propName="value"/>, element);
 	React.render(<ComponentName/><div>child</div></ComponentName>, element);
 ```

# Career Growth

## Exciting things to focus on
 - Develop tools
 	- these guys have a good background in tool development and it seems to help become a better programmer

# Tools
**Webpack** is a build tool: bundler and does live-reload and ES6 transpiling
Learn **VIM** and **MacVIM** and become a power-user
**DOMListener** DevTools plugin

# General Tips

## To fix `sudo npm install`
 1. `sudo rm -rf ~/.npm`
 2. Repeat for `node_modules` and any other affected directories
 3. `npm install` (never use `sudo`)
 ## $0 gets the element sleected in Chrome dev tools
 ## add `debugger` into code and then you can see the function calls it gets turned into

