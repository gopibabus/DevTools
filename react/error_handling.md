# 🔥Error Handling in React

* We handle errors in React using **error boundaries**. With an error boundary, you isolate parts of the app and handle errors locally.

* An error boundary is a React component that implements the **componentDidCatch()** lifecycle event, and wraps other components.

```js
class ErrorHandler extends React.Component {
  constructor(props) {
    super(props)
    this.state = { errorOccurred: false }
  }

  componentDidCatch(error, info) {
    this.setState({ errorOccurred: true })
    logErrorToMyService(error, info)
  }

  render() {
    return this.state.errorOccurred ? <h1>Something went wrong!</h1> : this.props.children
  }
}
```

You should use ErrorHandler in the following way:

```html
<ErrorHandler>
  <SomeOtherComponent />
</ErrorHandler>
```

> When an error happens inside **SomeOtherComponent** or other child components, and in the whole components subtree that they hold, **ErrorHandler** is going to intercept it, and you can handle the error gracefully.

[🌐 Reference](https://flaviocopes.com/react-handle-errors/)
[🌐 React Documentation](https://reactjs.org/blog/2017/07/26/error-handling-in-react-16.html)