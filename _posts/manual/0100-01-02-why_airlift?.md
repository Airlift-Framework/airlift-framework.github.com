---
layout: manual
title: Why Airlift?
abstract: The history of Airlift and why you should use it.
prose_link: http://prose.io/#Airlift-Framework/airlift-framework.github.com/edit/master/_posts/manual/0100-01-01-why_airlift?.md
author: Serena Lei
categories: manual
published: true
---

| [Introduction](#20_introduction) | [Cloud Computing](#21_cloud_computing) | [A Brief History](#22_a_brief_history) | [Airlift Concepts](#23_airlift_concepts) 


# 1.0 Introduction


Airlift is an open web framework for building restful web applications using functional JavaScript.  To understand what this means, we will begin by explaining some background on cloud computing.  Then we'll explore what goals the developers wanted Airlift to achieve.  The inner workings of Airlift will be detailed with a diagram.  At the end of this page you should understand what Airlift is capable of, why you should use it,

# 1.1 Cloud Computing

Cloud computing is the dynamic delivery of resources and services through the internet.  Due to its cost effectiveness, flexibility, and global accessibility, more and more companies are outsourcing their IT needs to seemingly virtual third party servers.  Instead of executing computations on a personal computer, through the cloud, a network of remote servers can provide scalable computing power.  These servers can store, manage, and process data using the internet as a medium.  When we check our email, collaborate on a project with Google Docs, or add an item to our Amazon cart, we are utilizing services on the cloud.

## Service Levels

Cloud computing consists of three tiers: infrastructure, platform, and software.  

* **Software as a Service (SaaS)** are applications designed for end-users and delivered over the internet. 
* **Platform as a Service (PaaS)** are tools designed to simplify and expedite the creation and delivery of software. 
* **Infrastructure as a Service (IaaS)** are the outsourced, on-demand resources that provide computing power through servers, storage, network, and operating systems.

![](/images/manual/CloudComputing_logos_Web.png)

At the lowest level, IaaS provides computing power that one can rent.  By outsourcing hardware, one does not need to fret over the investment, maintenance, power, and cooling of servers and networks.  IaaS is how data is stored on the cloud.  An example is Google Cloud Storage, which ensures that your data is safe, secure, and accessible.  Since your Google Spreadsheets and Calendar reminders are stored online in the cloud, if something were to obliterate your laptop, thankfully, your data would not be lost.

In the middle, PaaS provides foundations for developers to easily build and host applications.  An example of a PaaS platform is Google App Engine.  Such platforms provision hardware, and the developer need not worry about infrastructure components such as software upgrades, patches, and licensing.  With all this taken care of, a programmer may concentrate solely on his application, utilizing the underlying infrastructure to customize and specialize his code.  You can use PaaS platforms to develop SaaS applications.

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


# 1.2 A Brief History

<img src="/images/manual/Frustrated_Bedi_Web.png" style="float:left">

Airlift originated as the solution to the frustrations of a developer.  At the time, Java web application frameworks, such as Apache Struts, were not up to par with the developer's needs.  There had to be a better and faster way to build applications.  He traded in Java for a dynamic programming language, JavaScript.  He then began excitedly experimenting with Hannibal, capable of building web applications by using Java applications on servlets called Rhino.  It didn't take long for the developer to successfully utilize the benefits of this servlet, and he realized the potential of taking the entire platform and putting it on the cloud environment.  No more would he need to defeat the obstacles of setting up his own server, buying his own hardware, and dealing with web hosting providers.  No more would he need to wait ages for his server to be set up and for his applications to deploy.  By hosting a platform on the cloud, all these hassles would be taken care of.  Thus, Airlift was born!

Airlift was designed to meet the following goals:

* It should be RESTful.  It should use the simplest approach towards creating web applications.  One should not have to spend time figuring out which modules are creating a particular page or what the actions were.  Creating a web application should be easy.
* It should use JavaScript. JavaScript is dynamically typed, allowing for faster development, and capability to use closures for interesting applications.  When JavaScript is used on the both the client and server side, code can easily be moved back and forth.
* It should be hosted on the cloud.  By taking advantages of what the cloud has to offer, it should do away with the frustrations of buying hardware, going to a web hosting provider, and waiting long periods of time while setting up a server.  Instead, it should be quickly and reliably scalable.

<img src="/images/manual/Happy_Bedi_Web.png" style="float:right">

Airlift, which satisfies the above specifications, is being successfully deployed today.  Lucid Technics is currently building and adding to Airlift, expecting to release version 2.0 by the end of 2013.  Future developments include making Dictation more robust and feature-rich, and continuing the tight integration to Google App Engine.  Any developer interested in rapidly putting together scalable applications on Google App Engine should definitely check out Airlift, especially if they are interested in using JavaScript on server side.  Lucid Technics aspires to make Airlift useful, reliable, and helpful to developers around the global network.


# 1.3 Airlift Concepts

Airlift is Lucid Technics’ open source rapid web development framework designed to work with cloud infrastructures.  Airlift can be used to rapidly build secure and scalable cloud applications.  Much of the software created using Airlift is generated from Dictation, Lucid Technics’ open source human readable business requirements language.

Using Dictation with Airlift, Lucid Technics can generate software to deliver many modes of business functionality that are often coded by hand.  These include common application functionality such as data formatting, data conversion, and data validation.  They also include more challenging application functionality, such as automatic data auditing, robust data encryption, user action undo and redo, and role based security.

This advanced code generation apparatus enables rapid deployment of web applications, thereby allowing one to spend less time on infrastructure code, and more time on business workflow requirements.

## The Airlift Environment

<img src="/images/manual/Airlift_Charts_Web.png" style="float:left">

Airlift requires Java, Ant, and the App Engine SDK.  Google App Engine supports apps written in several languages, but it only provides runtime environments for four: Java, Python, PHP, and Go.  Google App Engine allows apps to be built in any JVM-based interpreter or compiler, such as JavaScript.  Airlift incorporates [Rhino](https://developer.mozilla.org/en-US/docs/Rhino), an open source JavaScript engine, to convert JavaScript scripts into Java classes.  This way, any apps built with Airlift can be easily hosted and deployed on Google App Engine.

<br>
<br>
<br>
<br>
<br>

Airlift makes the web development process simpler.  The developer only needs to write a dictation file describing business logic and the handlers.  The Airlift framework takes care of the rest.  When deploying a web app, the following steps are executed:

1.  Ant acts as the orchestrator for the whole process.  It first calls [Dictation](http://www.lucidtechnics.com/projects/dictation.html), a language for describing business applications.
2.  app.dic, a document describing the business logic in English, is parsed by Dictation.
3.  Dictation converts the app.dic into a coding language and generates metadata: meta/r files, meta/a files, and AppProfile.java.
4.  Ant starts Google App Engine, running a local server.
5.  Google App Engine initializes Airlift,  a .jar file which contains a servlet called RestServlet.
6.  Airlift deploys your web application, hosted on the cloud!

The following diagram illustrates what the Airlift environment contains and how it deploys a web application.

![](/images/manual/Airlift_Environment_Web.png)


## JavaScript Functional Programming

Why did Lucid Technics decide to build Airlift for JavaScript?  A simple answer is to enable web applications to use the same language on both the client and server side.  That limits the options to JavaScript -- an easy choice.  By using the same language on both sides, code can be moved back and forth with little to no editting.  Other advantages truly make JavaScript a strong choice.  JavaScript is dynamically typed, which allows for faster development and greater flexibility in polymorphism and interactive applications.  JavaScript supports functional programming, as its functions are first class objects.  This enables developers to exploit the many interesting applications of closures.  Google App Engine does not directly support JavaScript, but Lucid Technics believed in JavaScript for restful web applications.  Therefore, Lucid Technics made the decision to incorporate Rhino into Airlift to use JavaScript with Google App Engine.

## REST

As defined by Roy Fielding, Representational State Transfer (REST) is an "architectural style for distributed hypermedia systems" (2000).  Restful web applications feature scalability of component interactions, generality of interfaces, independent deployment of components, and intermediary components to reduce interaction latency, enforce security, and encapsulate legacy systems.  Rest-style architectures generally consist of clients and servers, where clients send request to the server and the server answers with a response.  Rest is a predominant web API design model.

Airlift supports the development of restful web applications.  It implements the HTTP request methods, GET, POST, PUT, DELETE, and COLLECT, which are used for requests.  Requests and responses are built around the transfer of representations and resources.  Resources are addressable objects, like files and documents, and a resource's representation is documentation that captures the current or intended state of a resource.  Resources are the center of Airlift application development.  In Airlift, each resource is represented as a simple JavaScript object. Airlift provides many restful functions for manipulating these resources in the server side of web applications.

## Conclusion

Now the purposes and features of Airlift should be clear.  Airlift provides a restful JavaScript web application framework, designed to function with Google App Engine and cloud infrastructures.  If this sounds like the perfect tool for your web application development, or a framework that you would like to try, great!  We trust that Airlift will facilitate the rapid development of your scalable application on Google App Engine.  [Install Airlift now!](/manual/getting_started.html#11_installation)
