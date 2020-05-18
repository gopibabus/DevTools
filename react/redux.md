# 🔥Redux with React

<img src="./assets/images/react_redux_webpack.png" alt="react & redux & Webpack" width="700" height="400">

### ✳Data Flow(React vs Redux)

> React uses Unidirectional flow i.e., data is allowed to flow fro parent node to child nodes not other way around.

<img src="./assets/images/react_without_redux.png" alt="react & redux" width="700" height="400">

**Data Flow in React**

<img src="./assets/images/unidirectional.gif" alt="react data flow">

**Data Flow in React using Redux**

<img src="./assets/images/redux.gif" alt="react data flow">

[🌐Reference](https://medium.com/@alialhaddad/https-medium-com-alialhaddad-redux-vs-parent-to-child-2583c8e29509)

## ⚡What is Redux and Why Redux?

?> **Redux** is a predictable state container for JavaScript apps. Redux takes away some of the hassles faced with state management in large applications. It provides you with a great developer experience, and makes sure that the testability of your app isn’t sacrificed for any of those.

<img src="./assets/images/redux_process.png" alt="redux" width="700" height="300">

<img src="./assets/images/redux_state.png" alt="redux" width="700" height="300">

<img src="./assets/images/redix_life_cycle.png" alt="redux" width="700">

* Good for managing large state.
* Useful to share data between containers.
* Predictable State Manahement using 3 principles
    * Single source of truth
    * State is read only
    * Changes using pure functions.

[Reference](https://dev.to/radiumsharma06/abc-of-redux-5461)

## ⚡Pure functions

Pure functions are functions which obey two laws:

1. Given the same input, always return the same output.
2. Produce no side-effects.

* React and Redux reducer functions must be pure in order to ensure that your UI compenents render properly.

[🌐 Medium Documentation](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-pure-function-d1c076bec976)

## ⚡Flux design pattern

<img src="./assets/images/flux.gif" alt="flux" width="700">

Flux has four roles: 
* actions
* stores
* dispatcher
* views

?> **Actions** are simple objects with a **type** property and some data.

```js
{
    "type": "IncreaseCount", 
    "local_data": {
        "delta": 1
    }
}
```

?> **Stores** contain the application’s state and logic.

?> The **Dispatcher** acts as a central hub. The dispatcher processes actions (for example, user interactions) and invokes callbacks that the stores have registered with it. Dispatcher does not have much logic inside it and you can reuse the same dispatcher across projects.

?> **Views** listen for changes from the stores and re-render themselves appropriately. 

<img src="./assets/images/flux_flow.gif" alt="flux" width="700">

> The most important thing to note is that every change goes via an **action** through the **dispatcher**

## ⚡MVC vs Flux

<img src="./assets/images/mvc_v_flux.jpg" alt="flux" width="700">

1. The **Flow** of the app is essential to **Flux** and there are very strict rules that are enforced by the **Dispatcher**. In **MVC** the flow isn’t enforced and most MVC patterns implement it differently.
2. **Unidirectional flow**: Every change goes through the dispatcher. A store can’t change other stores directly. Same applies for views and other actions. Changes must go through the dispatcher via actions. In MVC it’s very common to have bidirectional flow.
3. **Stores** don’t need to model anything and can store any application related state. In MVC models try to model something, usually single objects.

## ⚡How to install Redux?

1. Run the following command in your command prompt to install Redux.

```bash
npm install redux
```

2. To use Redux with react application, you need to install an additional dependency as follows

```bash
npm install react-redux
```

3. To install developer tools for Redux, you need to install the following as dev dependency

```bash
npm install --save-dev redux-devtools
```

> If you do not want to install **Redux dev tools** and integrate it into your project, you can install Redux DevTools Extension for **Chrome** and **Firefox**.

[🌐 Redux Documentation](https://redux.js.org/basics/usage-with-react)

[🌐 How to configure Redux](https://medium.com/backticks-tildes/setting-up-a-redux-project-with-create-react-app-e363ab2329b8)

## ⚡Higher order functions

?> A **higher order function** is a function that takes a function as an argument, or returns a function. 

?> **First order functions**, which don’t take a function as an argument or return a function as output.

?> **.map(), reduce(), sort() and .filter()** functions take a function as an argument. They're both higher order functions.

[🌐 Medium Documentation](https://blog.bitsrc.io/understanding-higher-order-functions-in-javascript-75461803bad)

## ⚡Methods in Redux

[🌐 Freebootcamp Documentation](https://www.freecodecamp.org/news/a-beginners-guide-to-redux-9f652cbdc519/)

## ⚡Redux Middleware

First, let's look at a redux pattern without middleware:
1. An event occurs
2. An action is dispatched
3. Reducer creates a new state from the change prescribed by the action
4. New state is passed into the React app via props

Adding middleware gives us a place to intercept actions and run side effects before or after an action occurs. After dispatching an action, it will first go through the middleware, then into the reducer.

Our new pattern with middleware now looks like:
1. An event occurs
2. An action is dispatched
3. Middleware receives the action
4. Reducer creates a new state from the change prescribed by the action
5. New state is passed into the React app via props

<img src="./assets/images/middleware.webp" alt="middleware" width="700">

**Example: Custom Logger Middleware**
```js
import { createStore, applyMiddleware } from 'redux'
import todos from './reducers'

function logger({ getState }) {
  return next => action => {
    console.log('will dispatch', action)

    // Call the next dispatch method in the middleware chain.
    const returnValue = next(action)

    console.log('state after dispatch', getState())

    // This will likely be the action itself, unless
    // a middleware further in chain changed it.
    return returnValue
  }
}

const store = createStore(todos, ['Use Redux'], applyMiddleware(logger))

store.dispatch({
  type: 'ADD_TODO',
  text: 'Understand the middleware'
})
```

[🌐 Redux Documentation](https://redux.js.org/api/applymiddleware)

[🌐 Middleware Ecosystem - Redux](https://redux.js.org/introduction/ecosystem#middleware)

## ⚡Libraries

### ✳React Libraries

* [React Router](https://reacttraining.com/react-router/)

### ✳Utility Libraries

* [Ramda](https://ramdajs.com/)
* [Lodash](https://lodash.com/)
* [immutable.js](https://immutable-js.github.io/immutable-js/)

### ✳CSS Libraries

* [glamarous](https://glamorous.rocks/)
* [styled components](https://styled-components.com/)
* [css modules](https://github.com/css-modules/css-modules)

### ✳Component Libraries

* [Material UI](https://material-ui.com/)
* [Semantic UI React](https://react.semantic-ui.com/)

### ✳Static Websites

* [Gatsby.js](https://www.gatsbyjs.org/)

### ✳Server side Apps

* [next.js](https://nextjs.org/)

### ✳Redux Libraries

* [reselect](https://github.com/reduxjs/reselect)
* [Redux Saga](https://redux-saga.js.org/)