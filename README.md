![DOM](/img/dom.png)

# DOM Document Object Model

Basic DOM manipulation tips for frontend developers

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

💡**Tip:** *Objects have properties and methods. Methods are like functions and will always have a parentheses `()` where you may need to pass in a parameter. While properties are like variables and you can assign them something with equal sign `=`*

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

## Changing the DOM With User Interaction

So far you have been doing the DOM manipulation all at once. But when building web apps, you want to make your app user interactive. To do this we need **event listeners**.

Event listeners are special functions that hook into the elements and can wait for certain event to happen. This even could be a button click or a keyboard key press.

We will go slow by using a `click` event.

We want to make a change everytime someone clicks the button.

Start by writing your html file with at least two elements, one `<button>` element for the trigger, and one `<div>` element where the change will show.

```html
<button class='button'>Click Here</button>

<div class='content'></div>
```

Now open up your `script.js` and target both of these elements so we can manipulate them:

```js
const button = document.querySelector('.button')
const contentEl = document.querySelector('.content')
```

We need to hook an event listener with the `button` element so we can tell when it's being pressed.

Every element has a special method called `.addEventListener()` which handles the event mechanism.

The method will take two primary parameters, first is a string of the type of the event, the second is another function.

```js
button.addEventListener('click', function() {
  // Do something when button gets clicked
})
```

**Tip:** *JavaScript is a functional language where you can pass in another function as a parameter.*

Since we are listening for the **click** event, you supply the type `click`.

Inside the second function (that is called a callback function), we will write our code to make the DOM changes. It's called a callback function because it will run after the 'click' happened.

```js
button.addEventListener('click', function() {
  contentEl.textContent = 'Button Clicked!'
})
```

Now when you open up your app and click on the button, the event will fire, the function will run and the content `<div>` will be populated with the text.


## Show some love!

If you learned something new from this repo, please star ⭐ it on GitHub. You can also tweet to share with other people.

[![tweet](img/tweet.png)](https://twitter.com/intent/tweet?url=https://github.com/tamalweb/json&text=JSON%20explained%20in%20simple%20terms%20via%20@tamalweb)
