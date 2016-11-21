---
layout: post
title:  "Environment Variables"
date:   2016-11-17 13:18:20 +0000
categories: programming
---

# ENV Variables

I thought I’d do a quick, simple post on ENV Variables, as it’s something I learnt today and thought it’d be good to share! I’m explaining my personal experience with them, however I’m sure there’s cooler ways to use them or different scenarios in which they would come in handy.

So ENV (Environment) Variables are super useful if you need to store sensitive data, such as passwords or any sort of key you don’t want the general public to see. Obviously when using git, you’re regularly pushing your code (or at least you should be) and including this sensitive information in your code publishes it to the world, which obviously isn’t a great idea. So enter ENV Variables.

There are two ways to go about defining ENV variables. You can set them up from your command line following the example below. The ruby -e flag basically allows us to run ruby code on a single line and all we’re asking is to puts the ENV Variable with the name MY_PASSWORD, which returns exactly what we put. Awesome, it works!

<pre name="bae6" id="bae6" class="graf graf--pre graf-after--p">$ export MY_PASSWORD=123456  
$ ruby -e 'puts "#{ENV["MY_PASSWORD"]}"'  
$ => 123456 </pre>

The downside of this is when leaving your terminal session (as in quitting it) the session is wiped, as are all the variables that you may have set, so moving forward this probably isn’t the best way to do things and I found that out the hard way.

The second and more sustainable method of doing this is to simply create a separate file that hold all of our ENV variables. Assuming we are working on a project, we can simply create a new ‘.env’ file in the root directory, open it up and simply type what we did in the command line (minus the ruby code), like so:

<pre name="789f" id="789f" class="graf graf--pre graf-after--p">MY_PASSWORD='123456'  
MY_KEY='qwerty654321'  
MY_NUM='0987654321'</pre>

We’re almost done now, two (very important things) left to do. I should’ve probably mentioned this first, but you need to install the dotenv gem for this to work.

<pre name="4816" id="4816" class="graf graf--pre graf-after--p">$ gem install dotenv</pre>

This allows ruby to read your variables from your ‘.env’ file when including them in your code.

Lastly, **BEFORE** pushing your code, make sure to add your ‘.env’ file to your .gitignore file and, as the filename suggests, it’ll be ignored. Simple as that!

Now you can access your variables in your code by simply calling them, like so:

<pre name="5287" id="5287" class="graf graf--pre graf-after--p">def personal_info  
  number = ENV["MY_NUM"]  
  password = ENV["MY_PASSWORD"]  
  personal_key = ENV["MY_KEY"]  
end</pre>

This simple tool allows anyone to safely store private information, whilst still pushing their code to github.

For more information, head over to the [dotenv](https://github.com/bkeepers/dotenv) repo on github.
