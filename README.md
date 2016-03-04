# _tag.js
A lightweight tool for creating, and wrapping html elements. Create data-rich components and templates with ease. It is especially useful when repeating large data sets and was build for speed.

### Basic Usage
The _tag( ) function takes 3 parameters, for example _tag( element, content, attributes ). The content and attributes parameters are optional. The content parameter can be a string, number, variable, expession, array or even an other _tag ( more on that later ).
```javascript
var hello = _tag('h1', 'Hello World!');
document.body.appendChild( hello );
```

You can attach any attribute you want. The attribute parameter takes an object. The {'key':'value'} pairs should be strings or variables. Here's an example:
```javascript
var button = _tag('button', 'Submit', {'class':'jumbo-btn', 'data-id': productId } );
```

The content parameter can be set to null or an empty string "". Content  can be appened to it later.
```javascript
var dataTable = _tag('table', null, {'class':'data-table'} );
```

The style attibute is also valid, but as a best practice you should always use a class or id.
```javascript
var hello = _tag('h1', 'Hello World!', {'style':'font-family: "Arial", sans-serif; color:red'} );
```
### Nesting Tags
Below is an example of nesting _tags into other _tags. This uses 4 lines of code instead of 14 lines of javascript.
```javascript
var item1 = _tag('li','Orange', {'class':'no-bullet'});
var item2 = _tag('li','Apple', {'class':'no-bullet'});
var item3 = _tag('li','Banana', {'class':'no-bullet'});
var foods = _tag('ul', item1 + item2 + item3, {'id':'food-list'});
```
> Note: foods takes an expression as the second parameter for it's content.

### Creating and Nesting Mutiple Tags
You can also create multiple elements at the same time by passing an array in as content. You can then nest those elements into another _tag. Now instead of 14 lines of code, you have 2 lines. 
```javascript
var items = _tag('li',['Orange', 'Apple', 'Banana'], {'class':'no-bullet'});
var foods = _tag('ul', items, {'id':'food-list'});
```
Here is the output:
```html
<ul id="food-list">
   <li class="no-bullet">Orange</li>
   <li class="no-bullet">Apple</li>
   <li class="no-bullet">Banana</li>
</ul>
```
If you're still not conviced that _tag.js can save you time developing, look at the demo.html file for a powerful working example of what it is capable of.
