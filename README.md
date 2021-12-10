# VanillaChat v1.0.0
##### A simple chat web-app created with tradational Web technologies
## Table of contents
* [Technologies](#technologies)
* [Setup](#setup)
* [Demo](#demo)
* [Why I Created](#why-i-created)
* [What I Learned](#what-i-learned)
* [Bugs and Missing Features](#bugs-and-missing-features)
* [Future](#future)
* [Working Principle](#working-principle)

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
[Live Demo](http://erdum.42web.io/vanilla_chat) **Note:** Please don't abuse my innocent web-app

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
Because this web-app is not for practical use due to its horrible design, so I created its second version which is available on branch v2.0 of this repo

## Working Principle
This web-app has a single html file which consist of a simple form for sending messages and some basic layout elements, all the magic happens inside the javascript file
#### Working
* We are polling our Php scripts from javascript every single second
* Inside polling function we first sent a get request to the get.php file for getting all the messages from database
* Our get.php just dumping all the messages from database to the client then at client side we are checking all the messages for read flag
* Read flag is set on those messages which are sent by the client and not yet readed by the other client 
* After we found a message which has read flag set then we will check its sender id to insure that it is not sended by us, after that we will populate this new message to the incoming messages
* And then we will take the id of this new message and send it to update.php script which will unset the read flag of this new message and making it old message
* Inside the polling function we are also calling status.php script every second and we are sending the current UTC time of the client to the server
* By that our system determine if user is currently online or not along with that we are also sending status about our typing status 
