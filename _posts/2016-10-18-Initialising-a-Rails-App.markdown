---
layout: post
title:  "Initialising a Rails App"
date:   2016-10-18
categories: programming ruby rails
---
# Initialising a Rails App

I know there’s a million of these articles out there and even though it’s quite a straightforward process, I still find myself having to research how to do it. So I thought I’d write a quick post about my process and how I do it.

Firstly, lets go ahead and open up the terminal and install rails.

<pre name="0fdc" id="0fdc" class="graf graf--pre graf-after--p">$ gem install rails </pre>

I’ve decided to use RSpec and Postgres, so the next command intialises a new app where I specify the database and the fact that I’d like to turn off Rails’ built-in test suit.

<pre name="6c49" id="6c49" class="graf graf--pre graf-after--p">$ rails new YourApp -d postgresql -T</pre>

If you’d rather use Rails’ default testing suite and database, you can also initialise an app like so:

<pre name="80c4" id="80c4" class="graf graf--pre graf-after--p">$ rails new YourApp</pre>

This will do a whole bunch of stuff and setup your project with a load of files. Once this is all done, navigate to the project’s root directory and launch the server.

<pre name="1d95" id="1d95" class="graf graf--pre graf-after--p">$ cd YourAppsRootDirectory  
$ bin/rails s</pre>

This will launch the server on the default port (http://localhost:3000), when navigating to this page you should see a message welcoming you to Rails and confirming your server is up and running! If that didn’t work and you’re having trouble, depending on your computers configuration, you may need to create your databases and run a rake task.

<pre name="9cb0" id="9cb0" class="graf graf--pre graf-after--p">$ bin/rake db:create </pre>

### Test setup

As I mentioned earlier, I’ve gone with RSpec, with Capybara, as my preferred testing suite, however choose whichever your most comfortable with. First things first, in our Gemfile we should add the required gems. At this point we should also specify what ruby version we’ll be using.

<pre name="4093" id="4093" class="graf graf--pre graf-after--p">ruby '2.3.0'</pre>

<pre name="7fc9" id="7fc9" class="graf graf--pre graf-after--pre">group :test do  
  gem 'rspec-rails'  
  gem 'capybara'  
end</pre>

Once doing this, we should bundle to install those gems and use the RSpec install command to create a testing structure for us.

<pre name="7214" id="7214" class="graf graf--pre graf-after--p">$ bundle  
$ bin/rails generate rspec:install</pre>

Lastly, if you’re using Capybara, you’ll need to reuqire it in your rails_helper.rb file.

<pre name="cbfd" id="cbfd" class="graf graf--pre graf-after--p">require 'capybara/rails'</pre>

Now you’re all ready to write your first test and start creating your application!
