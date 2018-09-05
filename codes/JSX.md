# JSX

## What is JSX?

JSX is a syntax extension to JavaScript that allows React Elements to be written inside JavaScript using HTML tags.

Using JSX, we can create React Elements easily with HTML Tags:


    var element = <h1>Hello World!</h1>

Without JSX, the process is much slower and more verbose:


    var element = React.createElement(
        'h1',
        null,
        'Hello World!'
    )

## Using JSX with JavaScript Expressions

Curly braces can be used to embed JavaScript expressions into JSX.

The following are all examples of valid JavaScript expressions in JSX:

    var str = "World!" 

    var element =  <h1> Hello {str}</h1>

    var item = {
        name: "Cheese",
        price: 5
    }
    var element = <p>{item.name} : ${item.price} </p>

    var length = 20
    var width = 10

    function calculateArea(x,y){
        return x * y
    }

    var element = <div>The Area is: {calculateArea(length,width)}</div>

## Using JSX with Attributes

You can supply attribute values using a string literal surrounded by quotes:

    var element = <button className ="deleteButton"> Delete </button>

You can also supply attributes values by embedding a JavaScript expression using curly braces:

    var element = <img src ={product.imageURL}></img>

Do not surround curly braces with quotes. This will cause your expression to be treated as a string literal:

    //Do not do this
    var element = <img src ="{product.imageURL}"></img>

Some common HTML attributes are named differently in JSX. For example "class" becomes "className" because "class" is a reserved keyword in JavaScript. Furthermore, attribute names in JSX follow the camelCase naming convention so an HTML attribute such as fontsize would become fontSize in JSX.
## Using JSX with Empty Tags

If a HTML tag is empty, you can close it with a '/>' instead of using a closing tag.

For example:

    var element = <input className ="nameInput"/>

## Using JSX with a Style Object

The style attribute can be populated with a style object instead of a string literal

For example:

    var styleObject = {
        backgroundColor: 'red',
        color:'blue',
        fontSize: 25,
        width: 100
    }

    var element = <input style = {styleObject}/>

In this next example, the first set of curly braces is for the JSX expression while the second set of curly braces is for the style object:

    var element = <input style = {{width:200,height:100}}/>

## Using JSX with Nested Elements

React Elements can be nested within other React Elements as long as the whole thing is wrapped by in a single element.

For example:

    var element = (
        <div>
            <div>Hello World</div>
            <div>Hello World</div>
        </div>

    )

This example is not surrounded with a single wrapping element and will throw an error:

    var element = (
        <div>Hello World</div>
        <div>Hello World</div>
    )

It is recommended to surround nested elements with paranthesis to avoid the problems that occur with automatic semicolon insertion.
## Using JSX Objects

Objects created with JSX can be manipulated just like normal JavaScript objects. They can be passed in arrays, used as arguments or return statements to functions and used inside if statements or for loops.

An example using JSX objects within an If Else statement:


    var product = {name:"apple",stock:0}

    if(product.stock < 0){
        var element = <h1>The product named {product.name} is not in stock</h1>
    }
    else{
        var element = <h1>The product named {product.name} and has {product.stock} units in stock</h1>
    }

    ReactDOM.render(
        element,
        document.getElementById("root")
    )