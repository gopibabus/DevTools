# 🔥Introduction to React

### ✳Components

<img src="./assets/images/atomic_components.png" alt="Atomic Components" width="700" height="400">

### ✳Data Flow(React & Redux)

> React uses Unidirectional flow i.e., data is allowed to flow fro parent node to child nodes not other way around.

**Data Flow in React**

<img src="./assets/images/unidirectional.gif" alt="react data flow">

### ✳Virtual DOM

<img src="./assets/images/virtual_dom.png" alt="Virtual DOM" width="700" height="400">

?> A virtual DOM object is a representation of a DOM object, like a lightweight copy.

When you try to update the DOM in React:

1. The entire virtual DOM gets updated.
2. The **virtual DOM** gets compared to what it looked like before you updated it. React figures out which objects have changed.
3. The changed objects, and the changed objects only, get updated on the **real DOM**.
4. Changes on the **real DOM** cause the screen to change.

### ✳create-react-app

<img src="./assets/images/create-react-app.png" alt="create-react-app" width="700">

**Create React App** is a comfortable environment for learning React, and is the best way to start building a new single-page application in **React**.

It sets up your development environment so that you can use the latest JavaScript features, provides a nice developer experience, and optimizes your app for production. You’ll need to have **Node >= 8.10** and **npm >= 5.6** on your machine.

**Create React App** doesn’t handle backend logic or databases; it just creates a frontend build pipeline, so you can use it with any backend you want. You don’t need to install or configure tools like **webpack** or **Babel**. They are preconfigured and hidden so that you can focus on the code.

**What comes with create-react-app?**

* A recommended starting folder structure
* A solid build setup with webpack and Babel (that you don't have to worry about setting up)
* Scripts to run our React application
* Extensibility

[🌐 create-react-app Documentation](https://create-react-app.dev/docs/getting-started/)

To Quick start React application usning **create-react-app**:

```bash
npx create-react-app my-app
cd my-app
npm start
```