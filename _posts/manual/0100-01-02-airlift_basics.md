---
layout: manual
title: Airlift Basics
abstract: Documentation for deploying your Airlift applicaton.
prose_link: http://prose.io/#Airlift-Framework/airlift-framework.github.com/edit/master/_posts/manual/0100-01-01-airlift_basics.md
author: Serena Lei
categories: manual
published: true
---

| [Introduction](#20_introduction) | [The Airlift World](#21_the_airlift_world) | [Dictation](#22_dictation) | [Handlers](#23_handlers) | [Code Generation](#24_code_generation) |

# 2.0 Introduction

In Airlift Basics, we will walk you through the steps of starting and finishing an Airlift application.  We'll explain more about what's inside the Airlift environment and how it all works together.  This page will describe how to write your business logic in the app.dic file and your handlers, which are the only two documents that you need to worry about for the server side.  After the developer's part is written, we can move on to deploying your first Airlift hello world application.


# 2.1 The Airlift World

Airlift provides a framework for web applications.  Many files and folders are already set up.

In the downloaded airlift folder, there are four JavaScript modules: dictate.js, hack.js, packages.js, and test.js.  airlift/dictate.js will help to translate your english-written business logic into code.

In the build folder, there are five different types of build.  Whether the application is running on the desktop or in production mode, these build files can help to set up global variables and customize an environment.

The dictation file, where a developer writes his business logic, can be found at src/doc/app.dic .  If no changes were made to this file, the example inside describes the attributes of four resources: a person, an order, an order line item, and a product.

Airlift supports GET, COLLECT, POST, PUT, and DELETE requests.  Although basic functionality is provided, the developer may need to handle different resources in unique ways.  For each resource described in the dictation file, the developer may write handlers in war/WEB-INF/classes/handler.  For example, handlers for a person resource, such as get.js and post.js should be placed in war/WEB-INF/classes/handler/person.  Handlers for an order resource should be placed in war/WEB-INF/classes/handler/order.

The metadata that is generated is put in the war/WEB-INF/classes/gen/meta folder.  For each resource described in the dictation file, the resource metadata is placed in the meta/r folder, and the attribute metadata can be found in the meta/a folder.  By calling `ant runserver` on the example dictation file, both meta/a and meta/r will have order.js, orderlineitem.js, person.js, and product.js modules.

\[image to come: diagram of directory hierarchy\]

# 2.2 Dictation

## app.dic

## Resources


# 2.3 Handlers

## Rest

## Hello World


# 2.4 Code Generation

<!--
A resource handle is an identifier for a resource that is currently being accessed. Resource handles can be opaque, in which case they are often integer numbers, or they can be pointers that allow access to further information. Common resource handles are file descriptors and sockets.

The concept of a web resource is primitive in the Web architecture, and is used in the definition of its fundamental elements. The term was first introduced to refer to targets of uniform resource locators (URLs), but its definition has been further extended to include the referent of any uniform resource identifier (RFC 3986), or internationalized resource identifier (RFC 3987). In the Semantic Web, abstract resources and their semantic properties are described using the family of languages based on Resource Description Framework (RDF).

-->

