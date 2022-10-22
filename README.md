# react-cheatnotes

Resources

- [React from egghead.io](https://egghead.io/lessons/react-rerender-a-react-application-ea98531e)
- [React official docs](https://reactjs.org/docs/getting-started.html)

# React Fundamentals

- We generally mount all elements on top of the root element meaning a div with id root.
- ```React``` and ```React-dom``` are required for React.

We create react elements using ````React and React-dom```` to render the elements.

## How to create a React element

```javascript

<div id="root"></div>
const rootElement = document.getElementById('root');
const element = React.createElement('div',{
    children:"Hello bro"
    className : "container"
})

ReactDOM.render(element , rootElement);

```
- object passed to React.createElement is props object.
- children can be passed as an array.

- We don't write React like the above syntax and use JSX which is HTML like syntax in javascript.
- Generally browser doesn't understand the above syntax so we use Babel which converts it to something that browser understands.
- Babel will replace the JSX with Reacr.createElement


After Babel
```javascript

<div id="root"></div>
const rootElement = document.getElementById('root');
const element = <div className="container">Hello Works</div>
ReactDOM.render(element , rootElement);

```

### React Fragments

- React Fragments are used to add multiple React elements 

```javascript

<div id="root"></div>
const rootElement = document.getElementById('root');
const helloElement = <div className="container">Hello</div>
const worksElement = <div className="container">Works</div>
const element = React.createElement(React.Fragment,null,helloElement,"",worksElement);
OR
const element = <React.Fragment>{helloElement} {worksElement}</React.Fragment>;
ReactDOM.render(element , rootElement);

```


### Creating React elements

- Always create a react element/Component with capital letter.

## How is a component created which is reusable?

- we create a function which accepts props

```javascript

<div id="root"></div>
const rootElement = document.getElementById('root');
const Message = props = <div className="message">{props.children}</div>

const element=(
    <div className="container">
    Hello
    <Message>Bye Works!</Message>
    </div>
)
ReactDOM.render(element , rootElement);

```

### Default props

- propTypes is used to validate the type of Props that are passed to the component to render.
- propTypes are not part of React production version.


### Why React?

React only updates the div which has difference with respect to the previous change so no parent elements are effected


