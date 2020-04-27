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

