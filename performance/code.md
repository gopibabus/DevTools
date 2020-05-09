# 🔥Optimizing Code
<img src="./assets/images/optimize_code_1.png" alt="optimize code" width="700">

---

!> Parse, compile & executing JS code by browser takes siginificant amount of time. 

<img src="./assets/images/optimize_code.png" alt="optimize code" width="700">

[🌐 Website to test website performance](https://www.webpagetest.org/)

## ⚡Solutions
### ✳Ahead-of-time (AOT) compilation

?> [AOT](https://angular.io/guide/aot-compiler) converts your Angular HTML and Javascript code into efficient JavaScript code during the build phase before the browser downloads and runs that code. Compiling your application during the build process provides a faster rendering in the browser.

### ✳Avoid Blocking Main thread

?>**Use less animations** on websites to keep websites fast.

### ✳Minimize using 3rd party libraries
?> **Try to minimize dependency on 3rd party libraries** because browser takes siginificant amount of time to compile entiry library.

### ✳Avoid Memory Leaks

!> Please remove unused **event listners** from javascript code to avoid unnecessary event loops in the browser.

### ✳Code Splitting

<img src="./assets/images/code_splitting.png" alt="code splitting" width="700">

> [Lazy loading](https://developer.mozilla.org/en-US/docs/Web/Performance/Lazy_loading) is a strategy to identify resources as non-blocking (non-critical) and load these only when needed.

**Code-splitting** your app can help you **“lazy-load”** just the things that are currently needed by the user, which can dramatically improve the performance of your app. While you haven’t reduced the overall amount of code in your app, you’ve avoided loading code that the user may never need, and reduced the amount of code needed during the initial load.

?> 🎯 Example: [Code Splitting in React](https://reactjs.org/docs/code-splitting.html)

?> React added easy way to implement code splitting **React.lazy** - (Route centric code splitting)

?> 💡 [Component-centric code splitting in React](https://github.com/jamiebuilds/react-loadable) - Recommended Way 😃

Code-Splitting is a feature supported by bundlers like **Webpack, Rollup and Browserify** (via factor-bundle) which can create multiple bundles that can be dynamically loaded at runtime.

### ✳Avoid Multiple re-rendering in React Apps

?> ⚙ [React.PureComponent](https://reactjs.org/docs/react-api.html#reactpurecomponent), If we want a component to re-render whenever it receives new props. But it is good practice to leverage life cycle method **shouldComponentUpdate** to re-render the component. 

> There is nice little package called [why-did-you-render](https://github.com/welldone-software/why-did-you-render) to view rendering of components in the browser console. We can use this package to see unnecessary rendering of components in react app.

### ✳Tree Shaking

?> **Tree shaking** is a term commonly used within a JavaScript context to describe the removal of dead code.

[🌐 MDN Documentation](https://developer.mozilla.org/en-US/docs/Glossary/Tree_shaking)

[🌐 Google Documentation](https://developers.google.com/web/fundamentals/performance/optimizing-javascript/tree-shaking/)

[🌐 Webpack Documentation](https://webpack.js.org/guides/tree-shaking/)

### ✳Measure performance of React Apps

In order to measure performance of react apps in chrome developer tools, Append **?react_perf** to your app URL.

> ⚓ Example:  https://reactapp.com/?react_perf
