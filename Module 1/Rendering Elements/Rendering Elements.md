# Rendering Elements

## React Elements

React Elements are objects that represent a DOM node. They are written using a syntax extension named JSX which we will cover later in this module. React Elements are different than React Components, which we will also cover later in this module.


    var element = <h1>Hello World!</h1>

React Elements need to be rendered by the ReactDOM.render() method to appear in the DOM.

## ReactDOM.render()

The ReactDOM.render() method is used to render a React Element into a specified part of the HTML DOM. In most React applications, there is usually a single root node where everything gets rendered into, but you may use as many root nodes as you desire.

In this case, the `<h1>Hello World!</h1>` React Element is rendered into the DOM element with the id of "root".

   `<div id="root"></div>`


    ReactDOM.render(
        <h1>Hello World!</h1>,
        document.getElementById("root")
    )

## Rerendering the DOM using additional render() calls

Once a DOM is rendered, it will remain the same until another render() method is called.

The following example uses additional render() calls to update the displayed number:


    var num = 0;

    function updateNum(){

        ReactDOM.render(
            <div>{num++}</div>,
            document.getElementById("root")
        )
    }
    setInterval(updateNum,100)