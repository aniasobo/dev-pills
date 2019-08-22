# Selecting elements

`document.querySelector('.className');`  

`document.querySelector('[data-customTag]');`  

all html p elements: `document.querySelectorAll("p");`  

specific element with class: `document.querySelector("p.className");`  

`document.querySelector("#id");`  

get the first `<p>` element that is child of `<div>`:  
`document.querySelector("div > p");`  

first `<div>` element with `someAttr` attribute:  
`document.querySelector('div[someAttr]');`  

multiple selectors where only the first one will have style applied:  
`document.querySelector('h2, h3').style.backgroundColor = "red";`  

