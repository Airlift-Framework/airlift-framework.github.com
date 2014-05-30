---
layout: manual
title: Getting Started
abstract: A lucid introduction to Airlift's installation process, basic concepts, and 'Hello World'.
prose_link: http://prose.io/#Airlift-Framework/airlift-framework.github.com/edit/master/_posts/manual/0100-01-01-getting_started.md
author: Serena Lei
categories: manual
published: true
---

| [Introduction](#10_introduction) | [Installation](#11_installation) | [Setting Up](#12_setting_up) | [The Airlift World](#13_the_airlift_world) | [Dictation](#14_dictation) | [Handlers](#15_handlers) | [Hello World](#16_hello_world) | [Playing Around](#17_playing_around) |

# 1.0 Introduction

This page will cover how to get Airlift up and running on your system.  Once setup, we will walk you through the steps of starting and finishing an Airlift application.  We'll explain more about what's inside the Airlift environment and how it all works together.  You will learn how to write your business logic in the app.dic file and your handlers, which are the only two documents that you need to worry about for the server side.  After the developer's part is written, we can move on to deploying your first Airlift hello world application.


# 1.1 Installation

Installing Airlift is simple.  You just need to copy the Airlift directory onto your local machine.  This should only take a few minutes.  But before you do that, be sure that your system meets the following requirements:

* [OpenJDK](http://openjdk.java.net/) (or [Java 7](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html) for Macs)
* [Apache Ant](http://ant.apache.org/srcdownload.cgi)
* [Google App Engine SDK](https://developers.google.com/appengine/downloads#Google_App_Engine_SDK_for_Java)

All set?  Go ahead and download the zip file, and unzip it into whichever directory you so desire.

<br>

<a class="download" href="https://github.com/LucidTechnics/Airlift/blob/airlift_2.0_development/downloads/airlift-beta-0.70_rc_108_734-env.zip?raw=true">Download Airlift</a>

<br>

Now go into this folder from the command line and enter the following to complete the set up.

     ant init

This command creates multiple directories needed for an Airlift application.  For your reference, here is the [terminal output for ant init](/txt/init.txt).

That's it!  You should now have access to all that Airlift has to offer.  If you have any trouble downloading Airlift, please contact us at info@lucidtechnics.com so we can help troubleshoot the problem.


# 1.2 Setting Up

The download button above provides a template hierarchy directory for a web application.  Inside the directory, many folders and files are already set up.  As the developer, you only need to worry about the business logic and the handlers.  In the dictation file app.dic (src/doc/app.dic), you can use plain english to describe your business logic.  You may write your own restful handlers for each class, resource, or domain in war/WEB-INF/classes/handler.  

Once you have finished writing the business logic and handlers.  From the command line, go into your web application directory and call:

     ant runserver

This will generate all the metadata that describes your resources, their attributes, and their security.  Here is an example [terminal output for ant runserver](/txt/runserver.txt).  With Airlift rapidly generating and taking care of datastore functions, you can spend more time concentrating on the user interface and business side of your application.

Now that Airlift is set up, you may go ahead and start fleshing out your web application.  In the next sections you will learn more about Airlift basics and how to go about writing a 'Hello World' application.


# 1.3 The Airlift World

Airlift provides a framework for web applications.  Many files and folders are already set up.

<img src="/images/manual/Env_Hierarchy_Web.png" style="float:left">

In the downloaded airlift folder, there are four JavaScript modules: dictate.js, hack.js, packages.js, and test.js.  airlift/dictate.js will help to translate your english-written business logic into code.

In the build folder, there are five different types of build.  Whether the application is running on the desktop or in production mode, these build files can help to set up global variables and customize an environment.

Within the src folder, the app.dic file, or dictation file, contains the business logic written in plain english.  This file can be found at src/doc/app.dic.  It describes the web application's resources and their attributes.

For each resource described in the dictation file, the developer may write handlers in war/WEB-INF/classes/handler.  Each resource could have its own set of handlers.

The metadata that is generated is put in the war/WEB-INF/classes/gen/meta folder.  For each resource described in the dictation file, the resource metadata is placed in the meta/r folder, and the attribute metadata can be found in the meta/a folder.  

Now that you know the structure of an Airlift application, let's walk you through a hello world application.  The helloworld application will set the web content to 'Hello, World' when the URL is retrieved.  After downloading the Airlift directory or making a copy of it, rename the folder to helloworld.  


# 1.4 Dictation

Dictation is an open source English-based domain-specific language for describing business applications.  It parses through a dictation file and generates metadata.

## app.dic

Open src/doc/app.dic.  If no changes were made to this file, the example inside describes the attributes of four resources: a person, an order, an order line item, and a product.  We wont be needing this, so you can go ahead and delete everything in this document.  Instead, copy and paste the following text into your dictation file.

     package example
     
     A Greeting
     can be viewed or collected or created or updated by all

In the helloworld dictation file, we describe one resource: a Greeting.  Following the declaration of a resource are descriptions of the resource's attributes.  What is great about dictation is that it is easy to read, write, and understand the various specifications about a resource.  We only need one resource for this helloworld application, but if you were to need multiple resources, all you would need to do is continue adding paragraph-like descritions of each resource.  Dictation files should have the following format:

     A(n) [resource name 1]
     [attribute description 1]
     [attribute description 2]
     [attribute description ...]
     [attribute description n]

     A(n) [resource name ...]
     [attribute description 1]
     [attribute description 2]
     [attribute description ...]
     [attribute description n]

     A(n) [resource name n]
     [attribute description 1]
     [attribute description 2]
     [attribute description ...]
     [attribute description n]


## Resources

Resources are the targets of uniform resource locators (URLs); they are files, documents, images and other objects of the web that can be located and accessed through the Internet.  

A dictation file lists all the resources of an Airlift application and their attributes.  The only specified attribute of a Greeting is that anyone can retrieve, read, and write to it.  Resources could have fields or properties such as a name, date, or price.  Attributes can also specify security roles, or who has what access to which resources, relationships between resources, and whether the resource contains static of dynamically updated data.  Describing resources in your a file entails describing the basic building blocks of a restful web application.


# 1.5 Handlers

A handler is a module that writes some data to the server response when a request is made to a web application.

Handlers process the request, compute data if necessary, and return a response to the client.  Airlift provides [rest modules](../api/#Rest) for basic functionality, but a developer may need to handle different resources in unique ways.  In a handler, a developer may define HTTP methods such as get, post, or delete.

For the helloworld application, we will create a get handler.  Within war/WEB-INF/classes/handler, create a folder called greeting.  Inside the greeting folder, use a text editor to create GET.js.  Insert the following code into your handler:

    exports.handle = function(_web)
    {
        _web.setContent("Hello, World"); 
    }

<img src="/images/manual/Handler_Web.png" style="float:left">

The function inside the handler handles an HTTP get request.  When a Greeting resource is retrieved, the handler sets the web content to "Hello, World".  

And that is all you need to write for a server-side hello world application!


# 1.6 Hello World

Now that everything is set up, simply open your command line, change directory into your helloworld folder, and enter `ant runserver`.

![](/images/manual/Dave_Gen_Web.png)

Metadata describing the greeting resource have been generated and placed into the war/WEB-INF/classes/gen/ meta/a and meta/r folders.  AppProfile.java, located at src/genjava/airlift/app has also been updated to describe the business logic.  The helloworld application is now hosted on localhost:8080.  To send a get request to a greeting resource, type the following into the address bar:

[http://localhost:8080/a/greeting/id](http://localhost:8080/a/greeting/id)

You should see a blank HTML page and the text, "Hello, World".

<img src="/images/manual/HelloWorld_Screenshot_Web.png" width="800">


# 1.7 Playing Around

At this point, feel free to play around and get a feel for Airlift.  In order to see small edits quickly, start the server with the following line:

     ant -Dairlift.env=desktop runserver

The desktop environment sets the cache to null, so you can immediately see all of your changes.

## Another quick example

In this example, we will retrieve the resource's id from the web and display it on the page.

In the helloworld application, we accessed a greeting resource with URL, http://localhost:8080/a/greeting/id.  We programmed the handler to set the web content to "Hello, World" when a greeting resource is requested.  That means any greeting resource produces this output.  Instead of having 'id' at the end of the URI, you could replace it with any identifier, such as 'monkey' or 'purple', and you would still see "Hello, World".  

Let's customize the response.  In the greeting get handler (war/WEB-INF/classes/handler/greeting/GET.js), replace the line \_web.setContent("Hello, World"); with the following:

    _web.setContent(_web.getId());

This updated handler will retrieve the id of the web resource by parsing its URL.  It then sets the web content to display the id.

Now, http://localhost:8080/a/greeting/monkey will display "monkey" and http://localhost:8080/a/greeting/purple will display "purple".

## Other resources

If you'd like to see some examples for inspiration, head over to the [demos](/manual/demos.html), or check out the [screencasts](/manual/screencasts.html).  If you are ready to start developing, please refer to our [API](/api) for a complete listing and description of Airlift functions.  Using Airlift, you should be able to breeze through the development of your web application.  Now go ahead and play on!
