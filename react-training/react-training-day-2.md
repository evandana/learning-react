<!-- MarkdownTOC -->

- [Developing ReactJS][developing-reactjs]
	- [Why React?][why-react]
	- [React Philosophy][react-philosophy]
	- [React Lifecycle][react-lifecycle]
	- [Classes?][classes]
	- [Bringing new tech into a feature set][bringing-new-tech-into-a-feature-set]
	- [Backbone TODO MVC][backbone-todo-mvc]
- [Flux][flux]
- [Animation][animation]
- [Router][router]
	- [Code Smells][code-smells]
- [Questions][questions]
- [TODO][todo]
- [Tips][tips]

<!-- /MarkdownTOC -->

<a name="developing-reactjs"></a>
# Developing ReactJS

<a name="why-react"></a>
## Why React?
 - **Accessibility** when you don't blow away all HTML, you can maintain focus
 - replace model layer with function calls to API
 - useful error messages in console, pointing to line of code

<a name="react-philosophy"></a>
## React Philosophy
 - What state do I have?
 - When do I change state?
 - Explicit over implicit

<a name="react-lifecycle"></a>
## React Lifecycle
 - [https://facebook.github.io/react/docs/top-level-api.html](Top Level API)
 - `componentWillMount` 
 - `componentDidMount` imperative things (measure an element or AJAX request for data)
 - `componentWillReceiveProps`
 - `shouldComponentUpdate`
 	- decide if you should or shouldn't update
 	- complicates it because now you have to consider time
 	- usually just slows down your app instead of thinking you're speeding it up
 - `componentDidUpdate` DOM has been updated
 - `componentWillUnmount` cleanup

<a name="classes"></a>
## Classes?
 - Should you use classes or just createClass?
 	- Easier to teach the one method we used instead of getting lost on discussions

<a name="bringing-new-tech-into-a-feature-set"></a>
## Bringing new tech into a feature set
 - Framework plans
 	- Ember has good upgrade path
 	- AngularJS has a reasonable plan
 	- ReactJS has a plan for implementation path
 - Should be able to work on individual components, not just feature trees
 	- Start at leaves and work towards trunk of feature tree, therefore not blocking extended branches

<a name="backbone-todo-mvc"></a>
## Backbone TODO MVC
 - consider not using inline JSX in the converted `.js file` for build processes
 - update the template as little as possible (focus on converting to ReactJS forst, one step at a time)
 - Use `{ expression ? ( <html></html> ) : null )}` for in-browser JSX transformer because `{ expression && (<html></html>) }` will return `0` if `false`
 - to fix whitespace bugs: `{ ' ' }`
 - change HTML `class` to JSX `className`
 - **Events**: pass in necessary callbacks/events as props and have a click handler trigger it
 	+ to send args/context `conClearCompleted: (x) => { this.onClearCompleted( x, a, b, c ) }`

<a name="flux"></a>
# Flux
 - Problem it solves
 	+ Notifications -> Home tab, +1 Notification comes back
 	+ Who's listening to events
 - What is it
 	+ Philosophy - set of rules to manage data
 	+ Force uni-directional data flow
 	+ VS Angular
 		* 2-way bindings and $scope
 - Flow
 	+ React View
 		* On Components
 		* `getInitialState`
 			- calls to store (looking back)
 		* `componentDidMount`
 			- moving forward
 	+ **Action Creators**
 		* Action is higher level (not click)
 			- more like "load" or "save" or "data failed to save"
 			- can have multiple side effects
 		* Are synchroneous
 			- do NOT make these ASYNC!
 			- View triggers "load contacts", api triggers "contacts loaded"
 	+ **Dispatcher**
 		* *Dispatch* actions (pub in pub-sub)
 		* *Register* callbacks (sub in pub-sub)
 			- Emits **CHANGE_EVENT**, but doesn't send the changed data
 		* Ensures only 1 action goes through at once
 	+ Summary
 		* Stores subsscribe to dispatchers
 		* Views subscribe to stores
 		* Actions should *NOT* trigger other actions
 	
<a name="animation"></a>
# Animation
 - animation is rendering based on state, which is basic ReactJS
 - [https://facebook.github.io/react/docs/animation.html#low-level-api-reacttransitiongroup](Low-level documentation)
 ```md
 	componentWillAppear(callback)
	This is called at the same time as componentDidMount() for components that are initially mounted in a TransitionGroup. It will block other animations from occurring until callback is called. It is only called on the initial render of a TransitionGroup.

	componentDidAppear()
	This is called after the callback function that was passed to componentWillAppear is called.

	componentWillEnter(callback)
	This is called at the same time as componentDidMount() for components added to an existing TransitionGroup. It will block other animations from occurring until callback is called. It will not be called on the initial render of a TransitionGroup.

	componentDidEnter()
	This is called after the callback function that was passed to componentWillEnter is called.

	componentWillLeave(callback)
	This is called when the child has been removed from the ReactTransitionGroup. Though the child has been removed, ReactTransitionGroup will keep it in the DOM until callback is called.

	componentDidLeave()
	This is called when the willLeave callback is called (at the same time as componentWillUnmount).
 ```
 - add `TransitionGroup component="ul"` to the parent
 - add "TransitionItem" component for the child that creates the right element
 - `this.getTweeningValue()` from `react-tween-state` will handle transitions as states change (this is a `mixin`)
 - [https://github.com/chenglou/react-motion](ReactJS Motion API)
 	+ more "natural" motion
 	+ [http://chenglou.me/react-motion/demos/demo8-draggable-list/](draggable list)
 - use callbacks for *sequencing*

<a name="router"></a>
# Router
 - [https://github.com/rackt/react-router](React Router)
 - 

<a name="code-smells"></a>
## Code Smells
 - `shouldComponentUpdate`
 - `forceUpdate`

<a name="questions"></a>
# Questions
 - Future of ReactJS
 - JSXTransformer production alternatives?
 - Architecture style guide like John Papa's for Angular?

<a name="todo"></a>
# TODO
  - Research **Oreillei** (AngularJS 2.0 split)	
  - Research [https://greensock.com/](Greensock) aka "GSAP"
  - Research [Velocity](http://julian.com/research/velocity/)
  - Research angularmeractimerbone

<a name="tips"></a>
# Tips
 - `window.postMessage` in `iFrames` for hacky-solutions
 - `mixins` are on their way out
 - Ember has a great router