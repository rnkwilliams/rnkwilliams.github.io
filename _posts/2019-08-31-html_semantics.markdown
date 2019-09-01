---
layout: post
title:      "HTML Semantics"
date:       2019-09-01 00:07:04 +0000
permalink:  html_semantics
---



Semantic HTML or semantic mark-up are elements used to describe what kind of content exists within a specific tag. It introduces meaning to the web page rather than just presentation and makes it clearer for both the developer and browser to understand.  Overall, it makes it easier to style pages, help search engines identify and categorize content on websites, and allows for easier styling of specific semantic elements when using CSS (Cascading Style Sheets).

 
Before HTML5, ```<div>``` tags were used to describe the type of content within the element. With the use of either id or class, developers was able to describe the content that element contained. 

Examples of non-semantic elements: ```<div>``` and ```<span>``` - Does not describe its content.

Layout using  ```<div>``` elements:
```
<div class="wrapper">
  <div id="header">
     <div id="nav">...</div>
 </div>
 <div id="main">
    <div id="music">
    <div id="hiphop">...</div>
    <div id="pop">...</div>
   </div>
<div id="footer">...</div>
```

After a while, [W3C (World Wide Web Consortium)](http://www.w3schools.com/) was able to turn those common descriptions into actual semantic elements eliminating the need to label so many div elements. Imagine a page full of div tags each with a description, things would get disorganized and messy fast! I would rather have descriptive HTML elements to arrange content vs using tons of div tags. W3C's goal was to make code more readable to developers and more descriptive for browsers.

Some examples of semantic elements:  
```
<article> <p> <aside> <details> <figcaption> <figure> <footer> <header> <main> <nav> <section> <summary> <time>``` 

These elements clearly define its contents and some of them even define parts of a web page to make it easier to organize HTML mark-up content and provide greater readability.

Layout updated using semantic elements:
```
<div class="wrapper">
  <header>
     <nav>...</nav>
  </header>
  <main>
    <section id="music">
      <article id="hiphop">...</article>
      <article id="pop">...</article>
    </section>
  </main>
	<footer>...</footer>
	```

As you can see, the use of semantic HTML makes it much easier to describe content used within an element rather than using a ```<div>``` or  ```<span>``` tag every time a description is needed. 

