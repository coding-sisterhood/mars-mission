# Agenda

1. Meet and Greet (~ 5 mins)

2. ReactJS presentation (~ 10 mins)

3. Workshop (~ 1.75 hours)

---

## ReactJS Presentation Notes

### What is React?

React is a declarative, efficient, and flexible JS library for building user interfaces.

### Prerequisites

- JavaScript (at least ES6)
- HTML
- programming concepts like functions, objects, arrays, etc

### DOM & Virtual DOM (ReactDOM)

#### DOM

DOM stands for Document Object Model and it is the structure representation of all nodes in HTML document. DOM provides a way for JavaScript to interact with every single node in an HTML document to manipulate it.

#### Virtual DOM

The Virtual DOM is an abstraction of the HTML DOM. It is lightweight and detached from the browser-specific implementation details. The Virtual DOM is React’s local copy of the HTML DOM. It allows React to do its computations and skip the real DOM operations.

#### How React utilises the DOM & virtual DOM

1. On first load, React will create the virtual DOM tree and the real DOM tree.

2. Before DOM gets updated, React takes a snapshot of the existing virtual DOM.

3. Once the virtual DOM has updated, React then compares the updated virtual DOM with the snapshot to find out _exactly_ which virtual DOM objects have changed.

4. React then updates the real DOM only for the objects that are changed in the virtual DOM.

React's process of comparing the two DOMs and updating the real DOM is called _reconciliation_. React uses _Diffing_ algorithm techniques of reconciliation.

#### ReactDOM

ReactDOM is a package that provides DOM-specific methods that can be used at the top level of your app. The most common method used is the `render()` method.

### Props

Props (short for "properties") **in React context** are parameters that a component takes in. This can be a confusing concept at first since it has the same name as the popular concept, 'property' or 'properties', in object oriented programming languages.

With props, React allows an application to handle data dynamically. Instead of hard coding your application, data gets passed into components as props and React will handle the rest (such as updating the data and re-rendering).

### State

Similar to props, state holds information that influences the render output. The key difference between the props and state is that props gets _passed_ into the component while state is managed **_within_** the component. To put simply, props are like function parameters while state is like variables declared within a function.

### Components

React focuses on modular programming/design where the application is made up of numerous small and isolated pieces of code called "components". There are a few different types of components, such as class components, function components, simple components, stateful components and stateless components.

Because of its modular design, React allows its code to be well-organised and reusable.

### JSX

JSX is short for JavaScript XML. With JSX, we can write code that looks like HTML, and also we can create and use our own XML-like tags. Using JSX is not mandatory for writing React as there are some things that run under the hood that renders the same information. While JSX looks a lot like HTML, it is actually closer to JavaScript.
