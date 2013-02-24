---
layout: api
title: Extensions
abstract: JavaScript module extensions that support Airlift utility modules.
author: Bediako George
categories:
- apis
published: true
---

# Introduction
Airlift is built on Rhino and App Engine.  Rhino is a fantastic JavaScript interpreter library written for Java.  App Engine is a fantastic platform as a service cloud environment that offers support for web applications programmed in Go, Python, and Java.

In order for Airlift to support server side JavaScript programming on App Engine we applied Rhino's capabilities to the App Engine environment.  To accomplish this we extended some of Rhino's libraries, and we added additional functionality to JavaScript's standard objects.  The following outlines the adaptations and improvements we made.

## - Function.prototype.partial (argument-1, argument-2, ..., argument-n)
Returns a wrapper function that wraps the function refered to by 'this'. The arguments passed into partial are stored to be applied when the wrapper function is invoked. When the wrapper function is invoked, its arguments are tacked on to the stored arguments.  If any of stored arguments are undefined, they will be filled in in the order of presentation of the wrapper function arguments.

 	var f0 = function(a1, a2)
	{
		return a1 + a2;
	};

	var f1 = f0.partial(undefined, ' Bediako');	

	util.println(f1('Hello')); //Hello Bediako
    
    
## - String.prototype.equalsIgnoreCase (String|java.lang.String _string)
Case insensitive comparison of a JavaScript string1 to another JavaScript or Java string.    Added as a convenience method, equalsIgnoreCase is merely a wrapper for java.lang.String.equalsIgnoreCase.

	var string1 = 'bediako';
    var string2 = new Packages.java.lang.String("Bediako");
    
    util.println(string1.equalsIgnoreCase(string2)); //true

## - String.prototype.replaceAll (String|java.lang.String _string1, String|java.lang.String _string2)
Replaces every occurrence of _string1 in 'this' with _string2.  Added as a convenience method, replaceAll is merely a wrapper for java.lang.String.replaceAll.

	var string1 = 'banana';
    
    util.println(string1.replaceAll("na", '')); //ba
