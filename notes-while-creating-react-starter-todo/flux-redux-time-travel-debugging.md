<!-- MarkdownTOC -->

- [Flux, Redux, &amp; Time Travel Debugging](#flux-redux-amp-time-travel-debugging)
    - [Context](#context)
    - [Flux](#flux)
    - [Redux](#redux)
    - [Time Travel Debugging](#time-travel-debugging)
    - [Resources](#resources)

<!-- /MarkdownTOC -->

<a name="flux-redux-amp-time-travel-debugging"></a>
# Flux, Redux, &amp; Time Travel Debugging

<a name="context"></a>
## Context

While at the [ReactJS conference](https://reactjs-training.com/), they described the programmer's holy grail:

> While you use an app, it tracks every state change. It could even replay a series of states. You could capture a series of states that produce an error, send this to QA, use it to debug and add this series to the testing suite. The result: **automatic test coverage for every defect found, without having to write the tests**.

Building on my previous simple [JSBin Todo App](http://output.jsbin.com/rahize) (based heavily on [TodoMVC's work](http://todomvc.com/examples/react)), I want to work towards that holy grail.

#### Key features

 - [Time Travel Debugging](#time-travel-debugging)
 - Experience with [Flux](#flux)/[Redux](#redux)

#### Credits
Huge credit and thanks go out to the eloquent and elegant explanations on [code-cartoons.com](http://code-cartoons.com) and by [Dan Abramov](http://stackoverflow.com/users/458193/dan-abramov) (see [Resources](#resources)). Read the articles, they are content-rich yet quite approachable. The notes you read below are my personal reminders about key concepts and should not be substituted for thorough research on these topics.


<a name="flux"></a>
## Flux

#### The Problem It Solves

Confusing data flows from event-driven, cascading, and asyc data updates triggered by models and views.

#### Its Solution

Unidirectional data flow pattern and a Dispatcher library. In essence: it is pattern of synchroneous hooks and async callbacks as directed by the Dispatcher.

#### Players

 - **Action Creator**
     + Creates an action (*type* and *payload*) and sends to *Dispatcher*
 - **Dispatcher**
     + Pass every action from *Action Creator* to all *Stores* (synchroneous)
 - **Store**
     + State and state changing logic
     + Uses a `switch()` statement based on *action type*
     + Emits a *change event* to *Controller View*
 - **Controller View**
     + Passes updated data to the *View*
 - **View**
     + Renders data to the DOM

#### Initialization and Data Flow Diagrams

I'm not going to try to summarize the great work already done. Follow these links: [initialization](https://code-cartoons.com/a-cartoon-guide-to-flux-6157355ab207#609c) and [data flow diagrams](https://code-cartoons.com/a-cartoon-guide-to-flux-6157355ab207#d130)

<a name="redux"></a>
## Redux

#### The Problem It Solves

Builds on the Flux solution with capabilities to:
 - Have better dev tools
 - Reload store files without erasing state
 - Allow for [time travel debugging](#time-travel-debugging)]
 - Provide easy access for 3rd party plugins

#### Its Solution

Those benefits are achieved by:
 - Separating the state data from state logic
 - Instead of just changing state, copy then change a state
 - Wrap parts for easy access and use a tree structure for state change logic

#### Players

 - **Action Creator**
     + Return a formatted *action object* to *Components*
     + (Do NOT send action to Dispatcher)
 - **Store**
     + Holds state
     + Delegates change logic to *Reducers*
     + Only 1 store
 - **Reducers**
     + Copy state
     + Update that copy
     + Pass back to Root Reducer
 - **Components**
     + *Smart Components*
         * In charge of actions
         * Pass methods to *Dumb Components*
         * Do not have their own CSS or DOM
     + *Dumb Components*
         * Have CSS and DOM
         * Receive actions through props from *Smart Components*
 - **View Layer Binding**
     + Connects *Components* to *Store*
         * *Provider Component*: Wraps and enables `connect()`
         * *`connect()`*: Provided by Redux and sets up *state* updates
         * *Selector*: Function that specifies the requried *state* properties
 - **Root Component**
     + Initializes app
     + Creates *Store* and indicates which *Reducers* to use
     + Brings together *View Layer Binding* and *Views*

#### Initialization and Data Flow Diagrams

I'm not going to try to summarize the great work already done. Follow these links: [initialization](https://code-cartoons.com/a-cartoon-intro-to-redux-3afb775501a6#a35b) and [data flow diagrams](https://code-cartoons.com/a-cartoon-intro-to-redux-3afb775501a6#cc8e)

<a name="time-travel-debugging"></a>
## Time Travel Debugging

By managing a history of states, Redux allows moving to any prior state.

Imagine being able to have the QA team send packaged up state historys so the dev team can automatically recreate the scenario exactly.

More eloquently and descriptively worded in this article: [Hot reloading and time travel debugging](https://code-cartoons.com/hot-reloading-and-time-travel-debugging-what-are-they-3c8ed2812f35).


<a name="resources"></a>
## Resources

 - [A cartoon guide to Flux](https://code-cartoons.com/a-cartoon-guide-to-flux-6157355ab207#.vbvrwcm14)
 - [A cartoon intro to Redux](https://code-cartoons.com/a-cartoon-intro-to-redux-3afb775501a6#.8810iq8iu)
 - [Hot reloading and time travel debugging](https://code-cartoons.com/hot-reloading-and-time-travel-debugging-what-are-they-3c8ed2812f35)
 - [StackOverflow: Redux VS Flux by Redux author](http://stackoverflow.com/questions/32461229/why-use-redux-over-facebook-flux/32920459#32920459)