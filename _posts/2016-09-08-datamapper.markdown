---
layout: post
title:  "DataMapper"
date:   2016-09-08
categories: database, programming
---
# DataMapper

Apologies for the massive delay between posts, it’s something I’m working on! I thought I’d do a very quick and simple post to explain something that I’d learnt recently, as we currently learning about databases. The example below assumes you would have created a database already using psql in your command line and stated that database in a separate datamapper_setup.rb file.

We are using Datamapper as our ORM (Object Relational Mapper), mainly because it’s quite easy to use (I’ve been told). Why can’t we just use Ruby to access our database stuff though? Because the database is written in SQL and it won’t understand what Ruby is asking of it. Enter Datamapper! All DataMapper does is basically allow us to call methods, using Ruby, to Create, Read, Update and Delete items in our database (CRUD — see other post).

<pre name="e265" id="e265" class="graf graf--pre graf-after--p">class Books  

  include DataMapper::Resource     

  property :id,     Serial     
  property :title,  String  
  property :author, String

end

</pre>

<pre name="0166" id="0166" class="graf graf--pre graf-after--pre"># Using DataMapper, you can now create a new book:

user = User.create('DataMapper','Data')</pre>

This very simple example illustrates a Books table, that stores the title and author of a book. Using the ‘create’ method, we are able to create a new record, which is then saved in the database. DataMapper does all the SQL conversion for us, so when navigating to our database in the command line, we would see a new book called ‘DataMapper’, with an author ‘Data.’ ID is simply just a number referring to the row and it’s serialised and increments automatically every time a new entry is created.

Obviously it’s a lot more powerful than this, and has built in methods than can check the uniqueness of the the record, data type of the record and so on, it’s pretty cool and makes working with databases a lot easier!

If you’re interested, head over to the [datamapper](http://datamapper.org/) website to read and find out more.
