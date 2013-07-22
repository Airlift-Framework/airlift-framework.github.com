---
layout: manual
title: Getting Started
abstract: A basic lucid introduction to Airlift for a quick start-up.
prose_link: http://prose.io/#Airlift-Framework/airlift-framework.github.com/edit/master/_posts/manual/0100-01-01-getting_started.md
author: Serena Lei
categories: manual
published: true
---

| [Introduction](#Introduction) | [Cloud Computing](#Cloud_Computing) | [A Brief History](#A_Brief_History) | [Airlift Concepts](#Airlift_Concepts) | [Installation](#Installation) | [Setting Up](#Setting_Up) |

<p id="Introduction"></p>
# 1.0 Introduction

This page will be about getting started with Lucid Technic's Airlift.  We will begin by explaining some background on cloud computing.  Then we will cover how to get Airlift running on your system and setup so that you can start working with it. At the end of this page you should understand what Airlift is capable of, why you should use it, and be ready to rapidly start your first Airlift application.


<p id="Cloud_Computing"></p>
# 1.1 Cloud Computing

Cloud computing is the dynamic delivery of resources and services through the internet.  Due to its cost effectiveness, flexibility, and global accessibility, more and more companies are outsourcing their IT needs to seemingly virtual third party servers.  Instead of executing computations on a personal computer, through the cloud, a network of remote servers can provide scalable computing power.  These servers can store, manage, and process data using the internet as a medium.  When we check our email, collaborate on a project with Google Docs, or add an item to our Amazon cart, we are utilizing services on the cloud.

## Service Levels

Cloud computing consists of three tiers: infrastructure, platform, and software.  

* **Software as a Service (SaaS)** are applications designed for end-users and delivered over the internet. 
* **Platform as a Service (PaaS)** are tools designed to simplify and expedite the creation and delivery of software. 
* **Infrastructure as a Service (IaaS)** are the outsourced, on-demand resources that provide computing power through servers, storage, network, and operating systems.

![](/images/manual/CloudComputing_logos.png)

At the lowest level, IaaS provides computing power that one can rent.  By outsourcing hardware, one does not need to fret over the investment, maintenance, power, and cooling of servers and networks.  IaaS is how data is stored on the cloud.  An example is Google Cloud Storage, which ensures that your data is safe, secure, and accessible.  Since your Google Spreadsheets and Calendar reminders are stored online in the cloud, if something were to obliterate your laptop, thankfully, your data would not be lost.

In the middle, PaaS provides foundations for developers to easily build and host applications.  An example of a PaaS platform is Google App Engine.  Such platforms provision hardware, and the developer need not worry about infrastructure components such as software upgrades, patches, and licensing.  With all this taken care of, a programmer may concentrate solely on his application, utilizing the underlying infrastructure to customize and specialize his code..  You can use PaaS platforms to develop SaaS applications.

At the highest level, SaaS provides web access to commercial software.  An example of an SaaS web application is Gmail, which is free and web-based.  To use Gmail, users do not need to install any applications onto their local hard drives, as the application is provided through a web browser.  Since the software is hosted on the cloud, users can access their accounts from any location as long as they have internet and a browser.  

## Selling Points

* Cost-efficient

One of the main reasons companies are turning toward cloud computing is cost.  Small companies may have difficulty affording hardware and staff to set up and maintain servers.  Maintenance of data centers is taxing for even large companies.  Allocating too much hardware means wasted computing power, and wasted money.  Allocate too little, and clients may not have a satisfying experience.  Cloud services are pay-per-use; a company only needs to pay for services they use.

* Scalability

Cloud computing provides a way to increase or decrease capacities and capabilities by demand, without needing to maintain infrastructure, train personnel, or license new software.  As an application grows, companies can add storage, RAM, and CPU capacity as needed.  Highly scalable applications adjust to demands, provisioning more resources when an application has ten thousand users today and automatically downscaling tomorrow when it isn't as busy.

* Accessibility to Resources

Along with increasing capabilities, one has the option to handpick any of the services, software, and applications that will best suit his or her needs.  By using a one-to-many model, cloud computing makes its applications available for multiple users, clients, and devices.  This promotes efficiency, code reuse, and global accessibility. 

* Quick Deployment

With cloud computing, one need not worry about the time it takes to implement and deploy applications.  When an application is ready to go up on the web, it will be functional and ready to use within a few minutes.


<p id="A_Brief_History"></p>
# 1.2 A Brief History

Airlift originated as the solution to the frustrations of a developer.  At the time, Java web application frameworks, such as Apache Struts, were not up to par with the developer's needs.  There had to be a better and faster way to build applications.  He traded in Java for a dynamic programming language, JavaScript.  He then began excitedly experimenting with Hannibn(?), capable of building web applications by using Java applications on servlets called Rhino.  It didn't take long for the developer to successfully utilize the benefits of this servlet, and he realized the potential of taking the entire platform and putting it on the cloud environment.  No more would he need to defeat the obstacles of setting up his own server, buying his own hardware, and dealing with web hosting providers.  No more would he need to wait ages for his server to be set up and for his applications to deploy.  By hosting a platform on the cloud, all these hassles would be taken care of.  Thus, Airlift was born!

Airlift was designed to meet the following goals:

* It should be RESTful.  It should use the simplest approach towards creating web applications.  One should not have to spend time figuring out which modules are creating a particular page or what the actions were.  Creating a web application should be easy.
* It should use JavaScript.  JavaScript's functions are first class objects, supporting functional programming.  JavaScript is dynamically typed, allowing for faster development, and capability to use closures for interesting applications.  When JavaScript is used on the both the client and server side, code can easily be moved back and forth.
* It should be hosted on the cloud.  By taking advantages of what the cloud has to offer, it should do away with the frustrations of buying hardware, going to a web hosting provider, and waiting long periods of time while setting up a server.  Instead, it should be quickly and reliably scalable.

Airlift, which satisfies the above specifications, is being successfully deployed today.  Airlift had been used to fulfill the software requirements of Northern Virginia Area Health Center, Ez-XBRL Solutions, Clark Construction, and the Office of Personal Management.

Lucid Technics is currently building and adding to Airlift, expecting to release version 2.0 by the end of 2013.  Future developments include making Dictation more robust and feature-rich, and continuing the tight integration to Google App Engine.  Any developer interested in rapidly putting together scalable applications on Google App Engine should definitely check out Airlift, especially if they are interested in using JavaScript on server side.  Lucid Technics aspires to make Airlift useful, reliable, and helpful to developers around the global network.


<p id="Airlift_Concepts"></p>
# 1.3 Airlift Concepts
<!--
airlift world, js functional programming, rhino, rest, handlers, methods, serverside, spirit


A resource handle is an identifier for a resource that is currently being accessed. Resource handles can be opaque, in which case they are often integer numbers, or they can be pointers that allow access to further information. Common resource handles are file descriptors and sockets.

The concept of a web resource is primitive in the Web architecture, and is used in the definition of its fundamental elements. The term was first introduced to refer to targets of uniform resource locators (URLs), but its definition has been further extended to include the referent of any uniform resource identifier (RFC 3986), or internationalized resource identifier (RFC 3987). In the Semantic Web, abstract resources and their semantic properties are described using the family of languages based on Resource Description Framework (RDF).

Airlift is Lucid Technics’ open source rapid web development framework designed to work with cloud infrastructures. We use Airlift to rapidly build secure and scalable cloud applications. Much of the software created using Airlift is generated from Dictation, Lucid Technics’ open source human readable business requirements language.

Using Dictation with Airlift, Lucid Technics can generate software to deliver many modes of business functionality that are often coded by hand. These include common application functionality such as data formatting, data conversion, and data validation. They also include more challenging application functionality, such as automatic data auditing, robust data encryption, user action undo and redo, and role based security.

Our advanced code generation apparatus enables Lucid Technics to rapidly stand up your web applications, thereby allowing us to spend less time on infrastructure code, and more time on your business workflow requirements.
-->


<p id="Installation"></p>
# 1.4 Installation

Installing Airlift is simple.  You just need to copy the Airlift directory onto your local machine.  This should only take a few minutes.  But before you do that, be sure that your system meets the following requirements:

* [OpenJDK](http://openjdk.java.net/) (or [Java 7](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html) for Macs)
* [Apache Ant](http://ant.apache.org/srcdownload.cgi)
* [Google App Engine SDK](https://developers.google.com/appengine/downloads#Google_App_Engine_SDK_for_Java)

All set?  Go ahead and download the zip file, and unzip it into whichever directory you so desire.

<br>

<a class="download" href="https://github.com/LucidTechnics/Airlift/blob/airlift_2.0_development/downloads/airlift-beta-0.70_rc_108_734-env.zip?raw=true">Download Airlift</a>

<br>
<br>

That's it!  You should now have access to all that Airlift has to offer.  If you have any trouble downloading airlift, contact us at info@lucidtechnics.com.


<p id="Setting_Up"></p>
# 1.5 Setting Up


# This page is under construction!

We are currently working to make the getting started page available soon.  Thank you for your patience.

