---
layout: post
title:  "Javascript Object Constructor"
date:   2016-09-14
categories: programming javascript
---
# Javascript Object Constructor

As it’s my first week properly learning Javascript, I thought I’d start off with something fairly simple and something I think I understand.

There are a few different ways to define an object, lets look at the simplest and easiest way:

<pre name="7bf6" id="7bf6" class="graf graf--pre graf-after--p">var car {  
  colour = "Red";  
  model = "Lexus";  
  year = "2016"  
  seats = 5;  
  engineType = "Hybrid";  
};</pre>

Great! We have a lovely new car object that we can pass around, only problem is, it’s a single object. In the real world, we’re probably going to want many cars and all of these cars are going to have the same properties that are listed above, just with different values. That’s where constructors come in, the example below outlines how you would implement this using our car example.

<pre name="ae42" id="ae42" class="graf graf--pre graf-after--p">function car(colour, model, year, seats, engine) {  
  this.colour = colour;  
  this.model = model;  
  this.year = year;  
  this.seats = seats;  
  this.engineType = engine;  
}</pre>

<pre name="a3d1" id="a3d1" class="graf graf--pre graf-after--pre">var lexus = new car("Red","Lexus","2016",5,"Hybrid");  
var ford = new car ("Blue","Ford","2014",5,"Petrol");</pre>

<pre name="6f20" id="6f20" class="graf graf--pre graf-after--pre">console.log(lexus.colour); --> Red  
console.log(ford.year); --> 2014</pre>

This method allows you to have many objects of one base type, which is extremely helpful. The ‘console.log’ method does what it says really and logs what ever you pass in to the console, therefore when you pass the object ‘lexus’ with the property ‘colour’ it should return ‘Red’, as that’s what was defined.

You may be thinking ‘this’ refers to in the code block, thats a whole other debate and blog post. However, in this simple example, think of ‘this’ as the car. So when we’re setting colour we’re kind of saying car.colour = colour, ‘this’ just refers to the parent object. As I said though, this is a big subject and something that still confuses me, so probably best not to write anymore about it. As soon as I understand it, I’ll be writing a post on it!

Also another **key** point to take away is that whenever creating new objects from a base object, be sure to use the keyword **new**.This ensures you are assigning a new instance of the object with the arguments that you pass in. If you forget, it can create some weird problems, so yeah, just don’t forget.

That’s my brief understanding of using an object constructor in Javascript. As my knowledge grows, I’ll be sure to post more about it (and edit anything that I may have got wrong!)
