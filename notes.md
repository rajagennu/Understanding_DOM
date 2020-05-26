- To get all html elements of a html page, we can use `.all`

```js
let val ;
val = document.all;
```
`all` return all html elements in the form of an array, so you can extract elements using array index and all javascript array prototype methods are available.

```js
let html_tag ;
html_tag = document.all[0];
```

By using `document` object we can access other html objects presented in the html document

```javascript
let val ;
val = document.head ;
val = document.body ;
val = document.doctype ;
val = document.domain ;
val = document.URL;
val = document.characterSet ;
val = document.contentType ;

val = documents.forms ; // return forms array
val = documents.forms[0];
val = document.forms[0].id ;
val = document.forms[0].method ;
val = document.forms[0].action ;

val = documents.links ; // return links array
val = documents.links[0] ;
val = documents.links[0].id ;
val = documents.links[0].className ;
val = documents.links[0].classList ; //retuens array all classes of links[0]

val = documents.images;

val = documents.scripts;


val = documents.scripts[2].getAttribute('src') ;
// return script 2 src attribute 


// printing all scripts name 

lets scripts = document.scripts ;
let scriptsArr = Array.from(scripts);

scriptsArr.forEach(functions(script){
  console.log(script.getAttribute('src')); // return each scripts source attribute.
});

```

### Document Selectors for Single Elements 

- single element selectors 
- multiple element selectors 

### Get Element By ID 

select the element by the ID 

`document.getElementByID()`

assume id is as `task-title` 
```javascript
console.log(document.getElementByID('task-title').id);
console.log(document.getElementByID('task-title').className );

// change styling

document.getElementByID('task-title').style.background = '#333' ;
document.getElementByID('task-title').style.color = '#fff' ;
document.getElementByID('task-title').style.padding = '5px' ;
document.getElementByID('task-title').style.display = 'none' ;

// content 

document.getElementByID('task-title').textContent = 'Task List' ;
document.getElementByID('task-title').innerText = 'Tasks List' ;

document.getElementById('task-title').innerHTML = '<span style="color:red"> Tasks List </span>';

// trick 

// instead of typing document.getElementByID everytime, we can do as below 

const tt = document.getElementByID('task-title');

```

use these for dynamic functionality. 

### Document Query Selector 

Select any html element by anything 

```js

document.querySelector('#task-title'); // select by class
document.querySelector('.card-title'); // select by class 
document.querySelector('h5'); // select by tag , if multiple selects 1st one. 

document.querySelector('li').style.color = 'red'; // first li element will set to color red 

document.querySelector('ul li').style.color = 'blue';

document.querySelector('li:last-child).style.color') ="red";
document.querySelector('li:nth-child(3)').style.color='yellow';
document.querySelector('li:nth-child(4)').textContent = "Hello World";
document.querySelector('li:nth-child(odd)').style.background = '#ccc';
```

### DOM select multiple elements 

selectors that can select multiple elements.

`document.getElementsByClassName` 

```javascript
const items = document.getElementByClassName('collection-item'); // items will be an array of items with class as collection-item

items[0].style.color='red'; //first item color will be set 
items[3].textContent = "Hello";

const listItems = document.querySelector('ul').getElementByClassName('collection-item');

```

`document.getElementsByTagName`

```javascript
const lis = document.getElementByTagName('li'); // get elements html tag name
lis[0].style.color = "red";
lis[3].textContent = 'Hello';
```

Convert HTML collection into an array

```javascript
lis = Array.from(lis);
```

Template String 

```javascript
`${variable}`
```

`document.querySelectorAll`

```javascript
const items = document.querySelectorAll('ul.collection li.collection-item');

const liOdd = document.querySelectorAll('li:nth-child(odd)');
const liEven = document.querySelectorAll('li-nth-child(even)');

liOdd.forEach(function(li, index){
  li.style.background = '#ccc' ; // every odd will get this color
});

for ( var index = 0; index < liEven.length ; index++) {
  liEven[index].style.background = '#f4f4f4';
}

```

If any HTML collection has child items, you can list all child nodes using `childNodes`

```js
const list = document.querySelector('ul.collection');
val = list.childNotes ;
console.log(val);
```

child element nodes
```
val = list.children;
```

`.nodeName` - Give Node Name 
`.nodeType` - Gives Node type as per below chart 

1 - Element
2 - attribute 
3 - Text Node 
8 - Comment 
9 = Document itself 
10 = doctype 

Children of Children 

```javascript
val = list.children[3].children;
val = list.firstChild ;
val = list.firstElementChild ;

val = list.lastChild ;
val = list.lastElementChild ;
val = list.childElementCount ;  
```

Similar to Child we have Parent, sibling methods. Google them for more information. 

### Creating Elements 

```javascript

// create element 
const li = document.createElement('li');

// add class 
li.className = 'collection-item';

// add ID 
li.id = 'new-item';

// add attribute 
li.setAttribute('title', 'New Item');

// create text node 
li.appendChild(document.createTextNode('Hello'));

// create new link element 
const link = document.createElement('a');

// Add class
link.className = 'class-name';

// add inner HTML 
link.innerHTML = '<span> Hello </span><i class="fa fa-remove"></i>';

// Append li as child to ul 
document.querySelector('ul.collection').appendChild(li);

```

### Remove & Replace elements in DOM 

```javascript

// Replace element 

// create element 
const newHeading = document.createElement('h2');

newHeading.id = 'task-title';

newHeading.appendChild(document.createTextNode('Task List'));

const oldHeading = document.getElementById('task-title');

const cardAction = document.querySelector('.card-action');

cardAction.replaceChild(newHeading, oldHeading);

console.log(newHeading);

// Remove Element 

const lis = document.querySelectorAll('li');
const list = document.querySelector('ul');

// Remove list item 
lis[0].remove();

// Remove child element 
list.removeChild(lis[3]);

// classes attr 

const firstLi = document.queryselector('li:first-child');
console.log(firstLi.children[0]);
const link = firstLi.children[0];

let val ;
val = link.ClassName ; // string of the classes
var = link.classList ; // DOM token list but with index. 
link.classList.add('test'); // remove : .remove('test')
val = link; 

// attribute 

val = link.getAttribute('href');
val = link.setAttribute('href','http://google.com');
val = link.hasAttribute('href'); // true / false 
link.removeAttribute('title');

```

### Events Listeners and The Event Object.



