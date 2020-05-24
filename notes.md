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

