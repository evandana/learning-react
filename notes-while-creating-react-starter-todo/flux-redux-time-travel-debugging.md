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
Huge credit and thanks go out to the eloquent and elegant explanations on [code-cartoons.com](http://code-cartoons.com) (see [Resources](#resources)). Read the articles, they are content-rich yet quite approachable. The notes you read below are my personal reminders about key concepts and should not be substituted for thorough research on these topics.


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

<a name="redux"></a>
## Redux

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

<a name="time-travel-debugging"></a>
## Time Travel Debugging


<a name="resources"></a>
## Resources

 - [A cartoon guide to Flux](https://code-cartoons.com/a-cartoon-guide-to-flux-6157355ab207#.vbvrwcm14)
 - [A cartoon intro to Redux](https://code-cartoons.com/a-cartoon-intro-to-redux-3afb775501a6#.8810iq8iu)
 - [Hot reloading and time travel debugging](https://code-cartoons.com/hot-reloading-and-time-travel-debugging-what-are-they-3c8ed2812f35)