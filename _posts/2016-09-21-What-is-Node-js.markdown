---
layout: post
title:  "What is Node.js?"
date:   2016-09-21
categories: programming javascript
---
# What is Node.js?


![](https://cdn-images-1.medium.com/max/800/1*-Nq1fQSPq9aeoWxn4WFbhg.png)

*[https://nodejs.org/en/about/resources/](https://nodejs.org/en/about/resources/)*


As this was my first week delving into the world of Node.js I thought I’d do a quick blog post explaining what it actually is, what it does, and why it’s cool.

So, what is this Node.js? In basic terms it’s a server side solution for Javascript, it allows you to build everything in the backend without having to change language to Ruby on Rails, for example. This is pretty cool because it allows someone to go full-stack using only one language, as most websites already use Javascript for their front-end.

Another cool thing (but quite confusing) is that it’s asynchronous, which basically means it can handle a lot of connections at once and does simple tasks such as reading and writing to databases super fast, which is quite important when building web applications. The only problem is that when running tests, all tests run and complete simultaneously, which is a bit of a problem. Imagine you’re using databases and trying to test a form on a webpage, you’d want to load the form, populate that form with text, write it to the database and then read and display it on a new page. Simple enough, however the problem is that this is all being done at the same time, so you’re expecting a page with text that hasn’t been saved in the database yet. That’s where callbacks come in. Simply put, callbacks just delay things, so we’d want the page to load, then we’d want to fill that form that’s been loaded, once that’s done we’d want to write the text to the database and so on… It’s just organising the order in which we want things to happen.

NPM (node package manager) is also pretty cool and has a load of modules that you can download and use in your program. There’s a variety available for both back and front end and they’ve been designed by the community in order to make everyones life that little bit easier. You can have a look at the vast array of packages available [here](https://www.npmjs.com/).

So yeah, thats my basic understanding of Node.js, it’s a server side solution using Javascript. There’s probably still a few blanks to fill in but for now, however, if you wish to find out more visit the website [here](https://www.npmjs.com/).
