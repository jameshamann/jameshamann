---
layout: post
title:  "What is AJAX?"
date:   2016-09-15
categories: programming
---
# What is AJAX?

Ajax is a technique for creating fast and dynamic webpages. It stands for Asynchronous Javascript and XML and allows data to be loaded into webpages without having to reload the whole webpage.

Before AJAX, users would have to manually refresh their mailboxes to check  
if they had any new emails. This would mean re-loading all of the HTML and CSS, which proved to be slow and ineffcient. Eventually the XMLHttpRequest API was made so that data could be passed between the server and the browser without having to reload the webpage.

Now, whenever we open our inbox in our browser, we don’t have to reload the page to check if we have a new email, AJAX gets the data from the server and passes it to our browser without having to reload the webpage, which is super helpful and efficient.

Using an Thermostat project as another example, whenever we update the location displayed by the weather API, (using jQuery’s ‘$.get())’ method), data is being passed between the browser and the server, using the XMLHttpRequest API, without having to refresh the webpage.

Another great example is Google. Ever notice that whenever you start typing to search something, google somehow auto-predicts what you’re searching for. That’s AJAX in action. The webpage isn’t being reloaded, instead a GET request is being fired off to the server over at Google, and the browser is receiving a JSON object, which contains all of the possible search results. This is then parsed and inserted into the bar, a lot is happening behind the scenes and it’s happening quite quickly.


<div class="aspectRatioPlaceholder is-locked" style="max-width: 680px; max-height: 160px;">![](https://cdn-images-1.medium.com/max/800/1*5AUZRL_75LYH3O3gu6e6ug.png)


This is happening every time you type a letter and below is the result after typing two extra letters to our previous example. As you can see, new results are displayed, meaning another GET request has taken place, and the browser has received another JSON object, containing potential searches. The more that’s typed in, the better google can predict what you’re searching for.


<div class="aspectRatioPlaceholder is-locked" style="max-width: 678px; max-height: 141px;">![](https://cdn-images-1.medium.com/max/800/1*LFW0XJN_PpJn-WFhwNfgrw.png)

It’s cool to think this is all happening behind the scenes is the space of a second. It’s made searching for things a lot quicker and easier, but it’s also kind of scary to think you don’t actually have to click ‘search’ for Google to know what you’re looking for. So, if you’ve ever thought of searching something, but never clicked the button, chances are the information was still passed over to Google!
