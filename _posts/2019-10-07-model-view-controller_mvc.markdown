---
layout: post
title:      "Model-View-Controller (MVC)"
date:       2019-10-08 01:22:35 +0000
permalink:  model-view-controller_mvc
---


When building web applications there are so many files and thousands of lines of code to keep up with that it would be impossible to keep everything in one big file. Your web application would be very disorganized, hard to read and it would be a headache to debug.

Thats where frameworks step in, like Sinatra, to help separate the application’s code by function and makes writing, reading, and debugging a piece of cake. 

To take this a step further, the Model-View-Controller paradigm is a popular three part software pattern to make it even simpler to organize and build frameworks for web applications. What exactly does each step represent? Let’s take a look.

* **Models**- Model code is the central component of the pattern that connects to the database and represents the main logic behind the web application. It defines the essential components of your app.

* **Views** - View code is considered the front-end component of the pattern and is what the user actually sees when using the web application. It makes your app look nice and is where the user interacts with it. Views are written in .erb files and consists of HTML and embedded Ruby, which is Ruby written within HTML.

* **Controllers** - Controller code is also written in Ruby and is the component that responds to the user input through browser requests called ‘routes’. Its considered the piece that ties Model and Views together, receiving user input and deciding what to do with it.

The MVC model is great for organizing your application’s files. The idea that applications should be divided into groups of files that have specific functions and interact with each other is referred to as separation of concerns. It is beneficial and makes writing, reading, and debugging your code much easier. 

