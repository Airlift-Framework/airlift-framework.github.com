---
layout: api
title: Collection
abstract: Collection module contains functions that can be used to traverse and process JavaScript arrays and Java collections in the same manner.
author: Bediako George
prose_link:
  http://prose.io/#substance/substance.github.com/edit/master/_posts/apis/0100-01-03-collection.md
categories:
- apis
published: true
---

# Introduction
The Collection module contains handy functions developers can use to traverse a JavaScript array, or a Java ArrayList or Java Set in a similar manner.

## - Every (collection, iterator, \[context\])
Returns true if all of the values in the list pass the iterator truth test. For JavaScript arrays, this function delegates to the native every function.

    var util = require('airlift/util');
    
    var users = ["Bediako", "Dave", "Loki"], c = require('collection');
    var success = c.every(users, function(_item, _index, _collection) { return true; });
    util.println(success); //true

## - Some (collection, iterator, \[context\]) ... alias Any
Returns true if any of the values in the collection pass the iterator's truth test. Short-circuits and stops traversing the list if a true element is found. If collection is a JavaScript array this function delegates to the native method some.

    var util = require('airlift/util');
    
    var users = ["Bediako", "Dave", "Loki"], c = require('collection');
    var r = c.some(users, function(_item, _index, _collection) { return (_index === 2); });
    util.println(r); //true
    
## - ForEach (collection, iterator, \[context\]) ... alias Each
Iterates over a collection of elements, yielding each in turn to an iterator function. The iterator is bound to the context object, if one is passed. Each invocation of iterator is called with three arguments: (item, index, collection). For JavaScript arrays this function delegates to the native forEach function.

    var util = require('airlift/util'), count = 0;
    
    var users = ["Bediako", "Dave", "Loki"], c = require('collection');
    c.forEach(users, function(_item, _index, _collection) { count++; });
    util.println(count); //3
    
## - Filter (collection, iterator, \[context\])
Looks through each value in the list, returning a collection of all the values that pass a truth test (iterator). For JavaScript arrays this function delegates to the native filter method.

    var util = require('airlift/util');
    
    var users = ["Bediako", "Dave", "Loki"], c = require('collection');
    var r = c.filter(users, function(_item, _index, _collection) { return (_index === 0); });
    util.println(util.json(r)); //["Bediako"]

## - Map (collection, iterator, \[context\])
Produces a new collection of values by mapping each value in the collection through a transformation function (iterator). For JavaScript arrays, the native map method is used.

    var util = require('airlift/util');
    
    var users = ["Bediako", "Dave", "Loki"], c = require('collection');
    var r = c.map(users, function(_item, _index, _collection) { return 'Hello ' + _item; });
    util.println(util.json(r)); //["Hello Bediako", "Hello Dave", "Hello Loki"]
    
## - Split (collection, iterator, \[context\])
Returns two collections.  The first collection contains the items for which _function returned true, the second collection contains the items for which the function returned false.

    var util = require('airlift/util');
    
    var users = ["Bediako", "Dave", "Loki"], c = require('collection');
    var r = c.split(users, function(_item, _index, _collection) { return _item.length > 4; });
    util.println(util.json(r)); //{success: ["Bediako"], fail: ["Dave", "Loki"] }
    
## - Partition (collection, attributeName)
Returns a value list (java.util.List or Javascript array) and a map (java.util.Map or Javascript object).  The value list contains, in the order they were discovered, the values that each item in the collection had on its property identified by attributeName.  The map's keys are the values found in the value list.  Each key points to the list of items that had that value on its property identified by attributeName.

    var util = require('airlift/util');
    
    var users = \[{name: "Bediako"}, {name: "Dave"}, {name: "Loki"}, {name: "Bediako"}\];
    var r = require('collection').partition(users, 'name');
    util.println(util.json(r)); //{keys: \["Bediako", "Dave", "Loki"\], partition: {"Bediako" : \[{name: "Bediako"}\], "Dave": \[{name: "Dave"}\], "Loki": \[{name: Loki}\]}}


