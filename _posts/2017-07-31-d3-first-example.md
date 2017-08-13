---
layout: post
title: "D3.js first example"
date: 2017-07-31
---

Example to use a parallel plot for the houseprices example. 
write code in VisualStudio. Run a python http server from the directory where the html is. open google chrome and go to localhost:8000. call html page. open google chrome dev tools to debug, change etc. as soon as happy enter code into VisualStudio and save. Refresh google chrome. 

D3.js - key learnings
- data has always to be transferred to the user. 
- grammar of graphics concept: instead of having tons of chart templates, build charts on basic buidling block such as rectangulars, circles etc. 
- hard to learn. not really because of D3.js itself. but because of various concepts that come together and have to fit: HTML, CSS, JavaScript and D3.js.
- book building on D3.js version 4.x - Interactive Data Visualization for the Web, 2nd edition by Scott Murray.

JavaScript Tutorial - key learnings from the W3Schools JavaScript tutorial

- HTML to define content, CSS to specify layout, JavaScript to program behavior
- case sensitive
- can change HTML attributes, styles
- placing scripts at the bottom of the <body> element improves the display speed, because script compilation slows down the display.
- hyphens (minus-zeichen. E.g. first-name) are not allowed in JavaScript. It is reserved for subtractions. Valid would be first_name etc.
- it is highly recommended to end statements with a semicolon. 
- == (only values, but not types will be compared) vs. === (strict comparison, values and types will also be compared)
- variable without a value is 'undefined'. 'null' is nothing, something that doesn't exist.
- Do NOT create global variables unless you intend to. In 'strict mode' automatically global variables will fail. 
- Arrays use numbered indexes (e.g. a[0]), objects use named indexes (e.g. a['name']). Array index starts with 0.
- Hoisting is JavaScript's default behavior of moving declarations to the top. Hoisting is JavaScript's default behavior of moving all declarations to the top of the current scope (to the top of the current script or the current function). JavaScript only hoists declarations (e.g. var x;), not initializations (e.g. var x = 5;). However, the var x from var x = 5 will be taken to the top. but x will be undefined until the line = 5 is reached. To avoid bugs, always declare all variables at the beginning of every scope. Since this is how JavaScript interprets the code, it is always a good rule.
- "use strict". 






