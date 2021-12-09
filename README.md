# RawChat v1.0.0
##### A simple chat web-app created with tradational Web technologies
## Table of contents
* [Technologies](#technologies)
* [Setup](#setup)
* [Demo](#demo)
* [Why I Created](#why-i-created)
* [What I Learned](#what-i-learned)
* [Bugs and Missing Features](#bugs-and-missing-features)
* [Future](#future)
* [How This Project Works](#how-this-project-works)

## Technologies
At the time of creating this project I only knew about basic web technologies
* Html 5
* Css
* Javascript
* Php
* MySql

## Setup
To run this project on localhost just clone this repo and put it inside your localhost htdocs folder

## Demo
[Live Demo](http://erdum.42web.io/raw_chat) **Note:** Please don't abuse my innocent web-app

## Why I Created
At the end of 2020 I want to make a project which will showcase my skills,for that reason I created a simple but effective client side web application which will show all of the knowledge I have at that time.

## What I Learned
* How to manipulate DOM with javascript
* How dynamic content is generated on client side
* How use polling to update data in realtime
* Difficulties in creating realtime web-app with Php

## Bugs and Missing Features
* [ ] I am using a non practical way of displaying both parties their online status and it is not working

## Future
Because this web-app is not for practical use due to its horrible design I created its second version which is available on branch v2.0 of this repo

## How This Project Works
This web-app has single html file which consist of a simple form for sending messages and some basic layout elements, all the magic happens inside the javascript file
#### Working
* We are polling our Php scripts from javascript every single second
* Inside polling function we first sent a get request to get.php file for getting all the messages from database
* Our get.php just dumping all the messages from database to client then at client side we are checking message all the messages for read flag
* Read flag is set on those messages which are sent by client and not readed yet by other client 
* After we found a message which has read flag set then we check its sender id to insure that it is not sended by us after that we will populate this new message to incoming messages
* And then send this message id to update flag script which will unset the read flag of this particular message
