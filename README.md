# DOM Document Object Model

Basic DOM manipulating tips for frontend developers

DOM is a huge topic, so I will only cover how to do basic manipulation in this doc.

By reading this doc, you will learn how to make things appear on screen programically.

## Targeting an Element

There is a global `document` object in JavaScript that allows you to handle all the document modifications.

You can select an item from the html using this method: `document.querySelector(".content")`

`querySelector()` is a method that takes a CSS class name or ID to target a specific element.

In the above example we are targeting an element with the class name of `.content`

There are other methods available to do the same thing, like you must have come across:

`document.getElementById()` -to select an item with an ID.

`document.querySelector()` is good because it let's us target elements using both class and ID's.

```js
// Targeting with class
document.querySelector('.some-class')
// Targeting with ID
document.querySelector('#some-id')
```

Once you have selected an element, save it in a variable in your JavaScript:

```js
const contentElement = document.querySelector('.content')
```

Now you can manipulate the element by referrencing the object `contentElement`

## Manipulating Element with Content

