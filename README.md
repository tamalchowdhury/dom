# DOM Document Object Model

Basic DOM manipulating tips for frontend developers

DOM is a huge topic, so I will only cover how to do basic manipulation in this doc.

By reading this doc, you will learn how to make things appear on screen programically.

## Targeting an Element

There is a global `document` object in JavaScript that allows you to handle all the document modifications.

You can select an item from the html using this method: `document.querySelector('.content')`

`querySelector()` is a method that takes a CSS class name or ID to target a specific element.

In the above example we are targeting an element with the class name of `.content`

There are other methods available to do the same thing, like you must have come across:

`document.getElementById()` -to select an item with an ID.

`document.querySelector()` is good because it let's us target elements using both class and ID's.

```js name=script.js
// Targeting with class
document.querySelector('.some-class')
// Targeting with ID
document.querySelector('#some-id')
```

Once you have selected an element, save it in a variable in your JavaScript:

```js name=script.js
const contentElement = document.querySelector('.content')
```

Now you can manipulate the element by referrencing the object `contentElement`

## Manipulating Element with Content

Since the `contentElement` is an HTML element, it will have a bunch of methods and properties you can use. 

The very first thing you can do with this element is to insert some text content using the `textContent` propery.

:::tip
Objects have properties and methods. Methods are like functions and will always have a parentheses `()` where you may need to pass in a parameter. While properties are like variables and you can assign them something with equal sign `=`
:::

```js name=script.js
contentElement.textContent = 'hello'
```

Now if you check your website, you will see you have added the `hello` text content. In the source it will be like: `<div>hello</div>` (for simplicity).

There is another property `.innerText` that does the same thing.

Now that you have added text, how about adding another HTML element inside this element?

You can do so with the `.innerHTML` property.

```js name=script.js
element.innerHTML = '<p>This works too!</p>'
```

Doing so you just added a new `p` tag with some text inside the original element:

`<div><p>This works too!</p></div>`


