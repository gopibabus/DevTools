# 🔥React

## ⚡Create a Component

?> Components let you split the UI into independent, reusable pieces, and think about each piece in isolation. Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called **“props”**) and return React elements describing what should appear on the screen.

### ✳Function Components

> The simplest way to define a component is to write a JavaScript function.

```js
function Welcome(props) {
	return <h1>Hello, {props.name}</h1>;
}
```

```js
function Welcome(props) {
	return <h1>Hello World!!</h1>;
}

function App() {
	return (
		<div>
			<Welcome />
			<Welcome />
			<Welcome />
		</div>
	);
}
```

### ✳Class Components

> You can also use an ES6 class to define a component

```js
class Welcome extends React.Component {
	render() {
		return <h1>Hello World!!</h1>;
	}
}

class App extends React.Component {
	render() {
		return (
			<div>
				<Welcome />
				<Welcome />
				<Welcome />
			</div>
		);
	}
}
```

[🌐 React Documentation](https://reactjs.org/docs/components-and-props.html)

## ⚡Add Styles to a Component

### ✳Inline Styling

> To style an element with the inline style attribute, the value must be a JavaScript object. Insert an object with the styling information.

```js
class Welcome extends React.Component {
	render() {
		return (
			<h1 style={{ color: 'red', backgroundColor: 'lightblue' }}>
				Hello World!!
			</h1>
		);
	}
}
```

!> In JSX, JavaScript expressions are written inside **curly braces**, and since JavaScript objects also use curly braces, the styling in the example above is written inside two sets of curly braces **{{ }}**. Use **backgroundColor** instead of **background-color**.

!> Since the inline CSS is written in a JavaScript object, properties with two names, like background-color, must be written with **camel case syntax**.

### ✳Using JavaScript Object

> You can also create an object with styling information, and refer to it in the style attribute.

```js
class Welcome extends React.Component {
	render() {
		const mystyle = {
			color: 'red',
			backgroundColor: 'lightblue',
		};
		return <h1 style={mystyle}>Hello World!!</h1>;
	}
}
```

### ✳Using CSS Stylesheet

> You can write your CSS styling in a separate file, just save the file with the .css file extension, and import it in your application.

```css
h1 {
	background-color: lightblue;
	color: red;
}
```

```js
import 'path/to/App.css';

class Welcome extends React.Component {
	render() {
		return <h1>Hello World!!</h1>;
	}
}
```

### ✳Using CSS Modules

?> The CSS inside a module is available only for the component that imported it, and you do not have to worry about name conflicts.

> Create the CSS module with the **.module.css** extension, example: **welcome.module.css**.

```css
h1 {
	background-color: lightblue;
	color: red;
}
```

```js
import 'path/to/welcome.module.css';

class Welcome extends React.Component {
	render() {
		return <h1>Hello World!!</h1>;
	}
}
```

[🌐 w3schools Documentation](https://www.w3schools.com/react/react_css.asp)

## ⚡Difference in Importing

```js
import React from 'react';
import Card from './Card';

const CardList = (props) => {
	const { robots } = props;
	const cardsArray = robots.map((user, index) => {
		return (
			<Card
				key={robots[index].id}
				id={robots[index].id}
				name={robots[index].name}
				email={robots[index].email}
			/>
		);
	});
	return <div>{cardsArray}</div>;
};

export default CardList;
```

?> In the above example, **react** is imported from **node_modules** folder. Whereas Card is our custom component. Difference is if we have to import anything from node_modules folder we specify name without preceding any **./**. If we have to import any files from our **src** folder then we should precede file name with **./**

## ⚡Export and Import Components

> Inorder to reuse(**import**) our components inside other components, we should **export** a component.

```js
import React from 'react';
import Card from './Card';

const CardList = (props) => {
	const { robots } = props;
	const cardsArray = robots.map((user, index) => {
		return (
			<Card
				key={robots[index].id}
				id={robots[index].id}
				name={robots[index].name}
				email={robots[index].email}
			/>
		);
	});
	return <div>{cardsArray}</div>;
};

export default CardList;
```

[🌐 React Documentation](https://create-react-app.dev/docs/importing-a-component/)

## ⚡Object Destructuring

### ✳Basic Assignment

```js
const user = {
	id: 42,
	is_verified: true,
};

const { id, is_verified } = user;

console.log(id); // 42
console.log(is_verified); // true
```

### ✳Assigning to new variable names

```js
const o = { p: 42, q: true };
const { p: foo, q: bar } = o;

console.log(foo); // 42
console.log(bar); // true
```

### ✳Assigning default values

```js
const { a = 10, b = 5 } = { a: 3 };

console.log(a); // 3
console.log(b); // 5
```

[🌐 MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

## ⚡Fragments in React

?> A common pattern in React is for a component to return multiple elements. **Fragments** let you group a list of children without adding extra nodes to the DOM.

```js
render() {
  return (
    <React.Fragment>
      <ChildA />
      <ChildB />
      <ChildC />
    </React.Fragment>
  );
}
```

```js
return (
	<>
		<ChildA />
		<ChildB />
		<ChildC />
	</>
);
```

[🌐 React Documentation](https://reactjs.org/docs/fragments.html)

## ⚡Key attribute

> **Keys** help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity.

```js
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) => (
	<li key={number.toString()}>{number}</li>
));
```

> The best way to **pick a key** is to use a string that uniquely identifies a list item among its siblings. Most often you would use IDs from your data as keys.

```js
const todoItems = todos.map((todo) => <li key={todo.id}>{todo.text}</li>);
```

[🌐 React Documentation](https://reactjs.org/docs/lists-and-keys.html#keys)

## ⚡props in React

> **props** (short for “properties”). **Props** are arguments passed into React components. Props are passed to components via HTML attributes.

```js
class Car extends React.Component {
	render() {
		return <h2>I am a {this.props.brand}!</h2>;
	}
}

class Garage extends React.Component {
	render() {
		const carname = 'Honda';
		return (
			<div>
				<h1>Who lives in my garage?</h1>
				<Car brand='Ford' />
				<Car brand={carname} />
			</div>
		);
	}
}
```

### ✳Props in the Constructor

> If your component has a **constructor** function, the props should always be passed to the constructor and also to the React.Component via the **super()** method.

!> **Note:** React Props are read-only! You will get an error if you try to change their value.

[🌐 W3Schools Documentation](https://www.w3schools.com/react/react_props.asp)

## ⚡state in React

?> React components has a built-in **state** object. The **state** object is where you store property values that belongs to the component.

?> When the state object changes, the **component re-renders**. The **state** object is initialized in the constructor.

```js
class Car extends React.Component {
	constructor(props) {
		super(props);
		this.state = {
			brand: 'Ford',
			model: 'Mustang',
			color: 'red',
			year: 1964,
		};
	}
	render() {
		return (
			<div>
				<h1>My {this.state.brand}</h1>
				<p>
					It is a {this.state.color}
					{this.state.model}
					from {this.state.year}.
				</p>
			</div>
		);
	}
}
```

### ✳Changing the state Object

?> To change a value in the state object, use the **this.setState()** method.

```js
class Car extends React.Component {
	constructor(props) {
		super(props);
		this.state = {
			brand: 'Ford',
			model: 'Mustang',
			color: 'red',
			year: 1964,
		};
	}
	changeColor = () => {
		this.setState({ color: 'blue' });
	};
	render() {
		return (
			<div>
				<h1>My {this.state.brand}</h1>
				<p>
					It is a {this.state.color}
					{this.state.model}
					from {this.state.year}.
				</p>
				<button type='button' onClick={this.changeColor}>
					Change color
				</button>
			</div>
		);
	}
}
```

### ✳Difference between state and props

?> **props** get passed to the component (similar to function parameters) whereas **state** is managed within the component (similar to variables declared within a function).

!> Always use the **setState() method** to change the state object, it will ensure that the component knows its been updated and calls the **render()** method.

[🌐 React Documentation](https://reactjs.org/docs/faq-state.html)

## ⚡Lifecycle Methods in a Component

> Each component has several **“lifecycle methods”** that you can override to run code at particular times in the process.

<img src="./assets/images/react_life_cycle.jpeg" alt="React lifecycle" width="700">

---

<img src="./assets/images/react_life_cycle.png" alt="React lifecycle" width="700">

[🌐 React Diagram](https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/)

### ✳Mounting

> These methods are called in the following order when an instance of a component is being created and inserted into the DOM.

1. constructor()
2. render()
3. componentDidMount()

**constructor()**

React constructors are only used for two purposes:

1. Initializing **local state** by assigning an object to **this.state**.
2. Binding **event handler methods** to an instance.

```js
constructor(props) {
  super(props);
  // Don't call this.setState() here!
  this.state = { counter: 0 };
  this.handleClick = this.handleClick.bind(this);
}
```

**render()**

> The **render()** method is the only required method in a class component. The **render()** function should be pure, meaning that it does not modify component state, it returns the same result each time it’s invoked.

!> **render()** will not be invoked if **shouldComponentUpdate()** returns false.

```js
render() {
	const { searchField, onSearchChange, robots, isPending } = this.props;
	const filterRobots = robots.filter((robot) => {
	return robot.name.toLowerCase().includes(searchField.toLowerCase());
});
return (
	<div className='tc'>
		<h1 className='f1'>RoboFriends</h1>
		<SearchBox searchChange={onSearchChange} />
		<Scroll>
			<ErrorBoundary>
				<CardList robots={filterRobots} />
			</ErrorBoundary>
		</Scroll>
	</div>
	);
}
```

**componentDidMount()**

> **componentDidMount()** is invoked immediately after a component is mounted (inserted into the tree). Initialization that requires DOM nodes should go here. If you need to load data from a remote endpoint, this is a good place to instantiate the network request.

```js
componentDidMount() {
    fetchPosts().then(response => {
      this.setState({
        posts: response.posts
    });
})
```

### ✳Updating

**render()**

**componentDidUpdate()**

> **componentDidUpdate()** is invoked immediately after updating occurs. This method is not called for the initial render. Use this as an opportunity to operate on the DOM when the component has been updated.

```js
componentDidUpdate(prevProps) {
  // Typical usage (don't forget to compare props):
  if (this.props.userID !== prevProps.userID) {
    this.fetchData(this.props.userID);
  }
}
```

### ✳Unmounting

**componentWillUnmount()**

> **componentWillUnmount()** is invoked immediately before a component is unmounted and destroyed. Perform any necessary cleanup in this method, such as invalidating timers, canceling network requests.

```js
 componentWillUnmount() {
    ChatAPI.unsubscribeFromFriendStatus(
      this.props.friend.id,
      this.handleStatusChange
    );
  }
```

### ✳Error Handling

**componentDidCatch()**

> This lifecycle is invoked after an error has been thrown by a descendant component. It should be used for things like logging errors.

```js
  componentDidCatch(error, info) {
    logComponentStackToMyService(info.componentStack);
  }
```

[🌐 React Reference](https://reactjs.org/docs/react-component.html#the-component-lifecycle)

## ⚡Children in React Component

> **Children**(this.props.children) allow you to pass components as data to other components, just like any other prop you use.

```js
var MyDiv = React.createClass({
  render: function() {
    return <div>{this.props.children}</div>;
  }
});

ReactDOM.render(
  <MyDiv>
    <span>Hello</span>
    <span>World</span>
  </MyDiv>,
  node
);
```

## ⚡Project Resources

[🗼Project](https://github.com/gopibabus/React-Redux)
[🌐 Users API Reference](https://jsonplaceholder.typicode.com/)
[🌐 Robots API Reference](https://robohash.org/robot_name)
