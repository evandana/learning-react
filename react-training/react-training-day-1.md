<!-- MarkdownTOC -->

- [Intro](#intro)
    - [Michael Jackson](#michael-jackson)
    - [Ryan Florence](#ryan-florence)
    - [Why React](#why-react)
    - [Stocks VS. Flows](#stocks-vs-flows)
    - [ES6](#es6)
- [React Basics](#react-basics)
    - [Events](#events)
    - [React.render()](#reactrender)
    - [State](#state)
    - [Components](#components)
- [Props VS State](#props-vs-state)
- [Testing](#testing)
- [Career Growth](#career-growth)
    - [Exciting things to focus on](#exciting-things-to-focus-on)
- [Tools](#tools)
- [General Tips](#general-tips)
    - [Other tips](#other-tips)
    - [Questions](#questions)

<!-- /MarkdownTOC -->
[local react-fundamentals folder](./react-fundamentals)

<a name="intro"></a>
# Intro

<a name="michael-jackson"></a>
## Michael Jackson
 - Father
 - MooTools, Twitter Ads platform, Immstruct

<a name="ryan-florence"></a>
## Ryan Florence
 - From Boston
 - CanvasLMS, Blackboard, EmberJS, react-router

<a name="why-react"></a>
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

<a name="stocks-vs-flows"></a>
## Stocks VS. Flows
 - Stocks: current value ($5)
 - Flows: rate of change (5mph)
 	- Must experience it to understand it (add time)
 	- Quote from Djikstra on dynamic process

<a name="es6"></a>
## ES6
 - Import
 - Fat arrow functions
 - Import
 - Restructuring
 	- var { select, option } = React.DOM // grabs those two props from React.DOM and sets the two vars to those values

<a name="react-basics"></a>
# React Basics
 - everything is a function

<a name="events"></a>
## Events
 - Not global
 - Handler defined in the component

<a name="reactrender"></a>
## React.render()

<a name="state"></a>
## State
 - Use a `state` object for tracking it
 ```javascript
 	var state = {
 		isOpen: false
 	};
 ```

<a name="components"></a>
## Components
 - Created with `React.createClass({})`
 - methods
 	- `setState`
 	- `getInitialState`
 	- `render`
 	- `getDefaultProps`
 - props
 	- `this.props.propName`
 	- `props.*`
 	- `props.children`
 		- children can be other components
	```javascript
	 	React.render(<ComponentName propName="value"/>, element);
	 	React.render(<ComponentName/><div>child</div></ComponentName>, element);
	```
 	- `propTypes` (*interface*! - what JS has been lacking!)
 		- essentially interface documentation, but shows warnings in console on errors
 		- can be enforced with `ESLint`
 		- custom prop types account for email validation, user
	```javascript
		// prop-types.js
		var userPropType = React.PropTypes.shape({
			name: React.PropTypes.string.isRequired,
			email: email.propType
		});
		// component-name.js
	 	propTypes: {
	 		title: React.PropTypes.string.isRequired,
	 		children: React.PropTypes.any,
	 		onToggle: React.PropTypes.func,
	 		users: React.PropTypes.arrayOf(userPropType)
	 	}
	```
	- `getDefaultProps` returns default prop
- **Controller components**
	- Wrap components and handle state or other attributes

<a name="props-vs-state"></a>
# Props VS State
 - **Props** do not belong to you, do NOT modify them. read or call their functions
 - **State** is an implementation detail of your Component
 - use `Component`'s `componentWillReceiveProps`
 - don't "synchronize state"
 - use **Controller Components** to manage state of a Component
 - naming conventions
 	- `stateless`, `stateful`, etc...

<a name="testing"></a>
# Testing
 - Don't test the `props` or `state` becuase they are not the **output** of the function
 - Test the DOM - the **output** of the function, what comes out of the `render` method
 - Tools / methodology
 	- Webpack (use the `04-Testing/exercise/tests.webpack.js`)
 	- Karma (use the `04-Testing/exercise/karma.conf.js` file as a template)
 	- Name all files `*.test.js`

<a name="career-growth"></a>
# Career Growth

<a name="exciting-things-to-focus-on"></a>
## Exciting things to focus on
 - Develop tools
 	- these guys have a good background in tool development and it seems to help become a better programmer

<a name="tools"></a>
# Tools
**Webpack** is a build tool: bundler and does live-reload and ES6 transpiling
Learn **VIM** and **MacVIM** and become a power-user
**DOMListener** DevTools plugin

<a name="general-tips"></a>
# General Tips

<a name="to-fix-sudo-npm-install"></a>
### To fix `sudo npm install`
 1. `sudo rm -rf ~/.npm`
 2. Repeat for `node_modules` and any other affected directories
 3. `npm install` (never use `sudo`)

<a name="other-tips"></a>
## Other tips
 * $0 gets the element sleected in Chrome dev tools
 * add `debugger` into code and then you can see the function calls it gets turned into
 * **Poor man's debugger**: `<pre>{JSON.stringify(state, null, 2)}</pre>`
 * `<collection>.**every**( item => item.val ) // is every item equal to that val`

<a name="questions"></a>
## Questions
1. Facebook ReactJS dev tools - asks for permission to view/edit data on visited webpages. Is this a security concern?
