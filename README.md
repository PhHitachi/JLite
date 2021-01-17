# JLite
JLite is javascript DOM library inspired by Jquery, this library is like mini version of Jquery

For testing you need to download the "[JLite.min.js](https://github.com/PhHitachi/JLite/blob/main/JLite.min.js)" files you can't use the raw of this github because have cors protection 


# Methods 

`addClass: ƒ (classes)`

`append: ƒ (html)`

`attr: ƒ (name, value)`

`click: ƒ (callback)`

`data: ƒ (name,value)`

`each: ƒ (callback)`

`extend: ƒ ()`

`hasClass: ƒ (classes, callback)`

`hide: ƒ ()`

`html: ƒ (val)`

`off: ƒ (name, callback)`

`on: ƒ (name, callback)`

`removeClass: ƒ (classes)`

`show: ƒ ()`

`text: ƒ (str)`

`toggleClass: ƒ (classes)`

`toogle: ƒ ()`


DOM Method selects HTML elements and perform actions on the selected element(s):

```
_(selector).action()
```
### Example

<h5>Show/Hide</h5>

```js
_('p').hide() //Hide selected elements

_('p').hide() //Show selected elements

_('p').toggle() //Toggle selected elements
```

<h5>add/remove/has (Classes)</h5>

```js
_('p').addClass('class1 class2') //addClass is allowed add mulitple class

_('p').removeClass('class1 class2') //removeClass is also allowed remove multiple class

//<p class="demo"></p>
//Note: the 'hassClass' method only check the first element this not available to check the multiple elements 
_('p').hasClass('demo') //Check selected element if have value 'demo' and return to true or false
```

<h5>EventListener</h5>

```js
_(selector).on(event,callback(this,event))
```

```html
<body>
  	<h1>Click me to hide me</h1>
	<script type="text/javascript" src="JLite.min.js"></script>
	<script type="text/javascript">
		_('h1').on('click', (_this, event) => {
			if(event.type == "click"){
				//for easy modify the element i return 'this' in callback
				//$(this).hide() = Jquery || The Jquery only return the event in callback
				//_this.hide() = JLite
				_this.hide()
			}
		});
	</script>
</body>
```

```js
//also you can use function() or ES6 arrow function
_('h1').on('click', function(e, n){
	if(n.type == "click"){
		e.addClass('class1 class2')
	}
});


_('h1').on('click', e => {
	e.addClass('class1 class2');
});

_('h1').on('click', (e, n) => {
	//console.log(n)
	e.addClass('class1 class2');
});

```

<h5>Element Events/handler</h5>

```js
_(selector).click(callback(this))
```

```js
//also you can use function() or ES6 arrow function
_('h1').click(function(e){
	e.addClass('class1 class2')
});

_('h1').click(e => {
	e.addClass('class1 class2')
});
```
