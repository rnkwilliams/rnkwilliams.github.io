---
layout: post
title:      "SINATRA - Comic Book Project"
date:       2019-10-12 22:08:38 -0400
permalink:  sinatra_comic_books_project
---


I’ll have to admit that this second time around, building this application was actually pretty fun! For project #2 I chose to build a Sinatra application for users to keep track of their  book collection. 

Sinatra is a web application framework and domain specific language (DSL) thats written in Ruby and is Rack based to allow your application to respond to HTTP requests through GET and POST routes. In addition to this framework, Active Record a Ruby library, was used which uses Object Relational Mapping (ORM) to create a database within the application. The Model-View-Controller (MVC) model was then used to keep the files organized and separate, but still be able to interact with each other through a concept called *separation of concerns* and the use of CRUD actions were used to create, read, update, and delete user inputs.



**THE PROCESS**

First things first, I created a chart to keep track of my table, which represented my models and their associations with each other.


|          users                                 |    comic_books          |
| ---------------------                | -------------------        | 
|   :username                              |      :publisher              |
|   :email                                        |      :title                         |
|   :password_digest                |   	:volume                |
|   (password)                              |     :year                       |
|	                                                       |    :user_id                |
| 	has_many :comic_books   | belongs_to :user |
	
	





**MODELS**
Based on the table, I have a User model and ComicBook model.

* USER - The User model has the following attributes: username, email, password. Please note that the password attribute is replaced with ‘password_digest’ as ‘password digest’ is required to use Bcrypt. Bcrypt is a gem that is used to protect the user's password and is secured as a salted hash (series of letters and numbers) to prevent hackers from stealing the user's password from the server. The User has_many :comic_books.

* COMICBOOK - The ComicBook model has the following attributes: publisher, title, volume, year and user id. The user_id is considered a foreign key since ComicBook belongs_to User.

Next the [Corneal](https://github.com/thebrianemory/corneal) gem was used to create the skeleton of my application, which is a Sinatra app generator. Instead of creating each file from scratch, the Corneal gem has the complete outline pre-made for you.  It includes everything needed to create your database, an app folder pre-set with Model-View-Controller (MVC) folders, gemfile, README, and preset controllers to create, read, update and delete (CRUD) user input. All that is left is creating your controller methods using the CRUD actions and the views that corresponds to each one.
