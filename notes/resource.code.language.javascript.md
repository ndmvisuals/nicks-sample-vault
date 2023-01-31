---
id: ardvbmxfz7le8wfg7bwkq89
title: JavaScript
desc: ''
updated: 1674935902426
created: 1674935902426
---

## Metadata
`url::` https://www.linkedin.com/learning/javascript-essential-training/javascript-the-soil-from-which-the-modern-web-grows?u=41910388

[Mix text and variables with template literals (linkedin.com)](https://www.linkedin.com/learning/javascript-essential-training/mix-text-and-variables-with-template-literals?u=41910388)
`tags::` #code, 
## Set up environment
- Visual Studio Code
	- Extensions
		- ritwickdey.liveserver
		- dbaeumer.vscode-eslint
		- esbenp.prettier-vscode
		

## The Landscape
- **Javascript**: the core language
	 - **ECMAScript**: instructions on how the browser should interpret Javascript. 
	 	 - Babel usually converts any Javascript written in "future javascript" to the present day standards
	- **Variation/Dialects**: introduce new features or opinions. 
		- *Ex. TypeScript*
	- **Frameworks**: allows writing of Javascript based front-end applications. Allows things to be done in a more streamlined way. 
		- *Ex. React, Vue, Angular.*
			- React used JSX (javascript xml) which specifices how to mix Javascript and HTML
	- **Build tools:**
		- helper applications that turn human-readable Javascript into something that the browswer can understand
		- *Ex. Babel, npm, WebPack, Gulp*
	- **Javascript server runtime**
		-  allows Javascript to be written on backend (on servers)
		- *Ex. Node.js*
				





## Javascript Basics
- define all variables, functions, and objects high up in the file before using it
- comments and verbose comments
	- ctrl + / at end of line 
- use indentation to show heicharchy
- semi colons are a human syntax, not required but its a preference thing
- script tag ``` <script></script>```  will encompass any javacode in html
- when browswer see's javascript it will stop everything and operate on it
- in head section
- javascript can be placed anywhere, but best practice to have it in its own document like css
- new tools in javascript should be **standard**
	- async
		- tells broswer to keep on parsing html while javascript file is downloading, and only stop html parsing when file is ready to be executed
		![[async 1.png]]
	- defer
		- downloads Javascript while HTML renders, but only executes at the end
		![[defer 1.png]]
- Javascript should always be loaded in teh head and async or defer should be used
- Javascript Modules
	- allow you to break out parts of code and import them in with a statement
	- If you do this, what ever is in the module will not be available in the browswer to actively work with. Therefore you have to be smart about what you put in module, *Ex. Classes*
```html
<!DOCTYPE html\>
<html lang\="en"\>
 <head\>
 <meta charset\="UTF-8" />
 <meta name\="viewport" content\="width=device-width, initial-scale=1.0" />
 <title\>Module demo</title\>
 <script type\="module" src\="backpack.js"\></script\>
 <script type\="module" src\="script.js"\></script\>
 </head\>
 <body\></body\>
</html\>
```
- when you set type as module, javascript will default to defer
```javascript
import backpack from "./backpack.js";
```
```javascript
export default backpack;

```

## Objects & Methods
### Concept
- An **object** in Javascript is the same as an object in real life
	- *Ex Backpack*
		- **property** of a backpack could be color, size, etc...
- **Prototypes**
	- collection of properties that define the object type
- **Methods**
	- property changing features, they exists in the object
	- act on the current method only, like opening a backpack only affects the backpack you are opening
### Code
- **Objects** are usually constants because contants can't be assigned to something else.
	- You can change the properties o f the object in the backpack, but backpack couldn't be transformed into the number 45 for example. 
	- Means you can't destory the objects when working with them
- **Properties** can only contain letters, digits, dollar signs, and underscores
	- use CamelCase for property names

Methods: functions sitting inside objects that perfomr actions on the properties of the object

Class: a blue print for an object

```javascript

/\*\*

 \* Creating classes:

 \*

 \* Class declaration: class Name {}

 \* Class expression:  const Name = class {}

 \*/

```
 
## Data Types and the DOM

## Methods Functions and Events