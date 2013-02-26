---
layout: api
title: Data Access
abstract: The Outgoing module contains functions used in the retrieval of data. Typically this is used when getting or collecting data from the datastore.
author: Bediako George
prose_link:
  http://prose.io/#substance/substance.github.com/edit/master/_posts/apis/0100-01-06-outgoing.md
categories:
- apis
published: true
---

# Introduction
The Outgoing module contains functions for processing retrieved data.  This includes functions for unencrypting data, and converting entities into JavaScript objects.  

## - Deentify (entity, value, attributeName)
Function designed to be used with resource.each, it converts an entity's property values into a JavaScript's objects attribute values.

    u = require('airlift/util'), out = require('airlift/outgoing');
	
    var person = {};
    var entity = out.createEntity('person', u.guid(12));
    entity.setProperty('fullName', 'Kwame Mtume');
    entity.setProperty('age', 37);
    
    var in = require('airlift/incoming'), res = require('airlift/resource'); 
    res.each('person', person, in.deentify.partial(entity));
    
## - Decrypt (entity, value, attributeName)
Function designed to be used with resource.each, it converts a resource's sensitive attribute values into encrypted property map values on an entity object.

    u = require('airlift/util'), out = require('airlift/outgoing');
	
    var person = {};
    var entity = out.createEntity('person', u.guid(12));
    entity.setProperty('fullName', 'Kwame Mtume');
    entity.setProperty('age', 37);
    
    var in = require('airlift/incoming'), res = require('airlift/resource'); 
    res.each('person', person, in.decrypt.partial(entity));