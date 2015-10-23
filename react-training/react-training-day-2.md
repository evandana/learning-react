<!-- MarkdownTOC -->

- [Why React?][why-react]
	- [React Lifecycle][react-lifecycle]
	- [Classes?][classes]
	- [Bringing new tech into a feature set][bringing-new-tech-into-a-feature-set]
	- [Backbone TODO MVC][backbone-todo-mvc]
- [Questions][questions]
- [TODO][todo]
- [Tips][tips]

<!-- /MarkdownTOC -->

<a name="why-react"></a>
## Why React?
 - **Accessibility** when you don't blow away all HTML, you can maintain focus
 - replace model layer with function calls to API

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

<a name="questions"></a>
# Questions
 - Future of ReactJS
 - JSXTransformer production alternatives?

<a name="todo"></a>
# TODO
  - Research **Oreillei** (AngularJS 2.0 split)	

<a name="tips"></a>
# Tips
 - `window.postMessage` in `iFrames` for hacky-solutions
