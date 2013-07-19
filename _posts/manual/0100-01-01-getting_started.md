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

At the lowest level, IaaS provides computing power that one can rent.  By outsourcing hardware, one does not need to fret over the investment, maintainence, power, and cooling of servers and networks.  IaaS is how data is stored on the cloud.  An example is Google Cloud Storage, which ensures that your data is safe, secure, and accessible.  Since your Google Spreadsheets and Calendar reminders are stored online in the cloud, if something were to obliterate your laptop, thankfully, your data would not be lost.

In the middle, PaaS provides foundations for developers to easily build and host applications.  An example of a PaaS platform is Google App Engine.  Such platforms provision hardware, and the devloper need not worry about infrastructure components such as software upgrades, patches, and licensing.  With all this taken care of, a programmer may concentrate soley on his application, utilizing the underlying infrastructure to customize and specialize his code..  You can use PaaS platforms to develop SaaS applications.

At the highest level, SaaS provides web access to commercial software.  An example of an SaaS web application is Gmail, which is free and web-based.  To use Gmail, users do not need to install any applications onto their local harddrives, as the application is provided through a web browser.  Since the software is hosted on the cloud, users can access their accounts from any location as long as they have internet and a browser.  

## Selling Points

* Cost-efficient

One of the main reasons companies are turning toward cloud computing is cost.  Small companies may have difficulty affording hardware and staff to set up and maintain servers.  Maintainence of datacenters is taxing for even large companies.  Allocating too much hardware means wasted computing power, and wasted money.  Allocate too little, and clients may not have a satisfying experience.  Cloud services are pay-per-use; a company only needs to pay for services they use.

* Scalability

Cloud computing provides a way to increase or decrease capacities and capabilities by demand, without needing to maintain infrastructure, train personnel, or liscence new software.  As an application grows, companies can add storage, RAM, and CPU capacity as needed.  Highly scalable applications adjust to demands, provisioning more resources when an application has ten thousand users today and automatically downscaling tomorrow when it isn't as busy.

* Accessibility to Resources

Along with increasing capabilities, one has the option to handpick any of the services, software, and applications that will best suit his or her needs.  By using a one-to-many model, cloud computing makes its applications available for multiple users, clients, and devices.  This promotes efficiency, code reuse, and global accessibility. 

* Quick Deployment

With cloud computing, one need not worry about the time it takes to implement and deploy applications.  When an application is ready to go up on the web, it will be functional and ready to use within a few minutes.



<!--
Amazon AWS notes
-"cloud computing" = the on-demand delivery of IT resources via the Internet with pay-as-you-go pricing.
-cloud computing services - accessed by the internet 
-aws has compute, storage, database services
-IT resources without capital investment
-services = pay as you go without upfront costs
-pay only for what you need
-add and remove capacity quickly - saves money + provide enough capacity for chees
-traditional data center - provision too many service -> waste money and time, too few -> customers dont have best experience
-scale up and down; autoscaling

cloud computing use cases
-web, mobile, & social apps
-big data: store and process large datasets
-backup & storage
-digital media: ingest, store, encode, protect, stream media
-enterprise applications
-gaming: deliver casual or MMO games


Google App Engine
-autoscaling without worrying about managing machines
-supercharge app with services such as Task Queue, XMPP, and Cloud SQL (google services use these)
-customize: manage your app with a simple, web-based dashboard
-App Engine = easy to build, maintain, and scale
-you can publish an app that people can use right away at no charge from Google and with no obligation
You may be outsourcing actual hardware, application development and hosting, or only wish to run online software from other providers.

Wikipedia
Cloud computing is a colloquial expression used to describe a variety of different types of computing concepts that involve a large number of computers that are conected through a real-time communication network (typically the Internet).[1] Cloud computing is a jargon term without a commonly accepted non-ambiguous scientific or technical definition. In science, cloud computing is a synonym for distributed computing over a network and means the ability to run a program on many connected computers at the same time. The popularity of the term can be attributed to its use in marketing to sell hosted services in the sense of application service provisioning that run client server software on a remote location.

 a way to increase capacity or add capabilities on the fly without investing in new infrastructure, training new personnel, or licensing new software. Cloud computing encompasses any subscription-based or pay-per-use service that, in real time over the Internet, extends IT's existing capabilities.

services offered by cloud computing: application, platform, infrastructure

-->

<p id="A_Brief_History"></p>
# 1.2 A Brief History


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


<!--

Circle headers: Getting Started, Airlift Basics, Dictation, App Engine Services, Customization, Demos

Getting Started
-cloud computing
-history
-airlift concepts
  -airlift world, js functional programming, rhino, rest, handlers, methods, serverside, spirit
-installation
-first-time setup

Airlift Basics
-modules
-writing a handler (returns hello world)
-creating a resource
-code generation

Dictation
-dictation
-resources
-handling resources

App Engine Services
-server
-airlift in other systems/clouds

Customization
-build script
-configuration

Demos
-links to screencasts
-registration
-social login


-->