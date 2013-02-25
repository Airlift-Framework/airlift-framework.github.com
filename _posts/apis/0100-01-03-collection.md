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
Returns true if all of the values in the list pass the iterator truth test. Delegates to the native method every, if present.

    var users = ["Bediako", "Dave", "Loki"], c = require('collection');
    var success = c.every(users, function(_item, _index, _collection) { return true; });
    util.println(success); //true

## - ForEach (collection, iterator, \[context\]) ... alias Each
Iterates over a collection of elements, yielding each in turn to an iterator function. The iterator is bound to the context object, if one is passed. Each invocation of iterator is called with three arguments: (item, index, collection). For JavaScript arrays this function delegates to the native forEach function if it exists.

    var count = 0;
    var users = ["Bediako", "Dave", "Loki"], c = require('collection');
    c.forEach(users, function(_item, _index, _collection) { count++; });
    util.println(count); //3
    
## - Filter (collection, iterator, \[context\])
Looks through each value in the list, returning a collection of all the values that pass a truth test (iterator). For JavaScript arrays this function delegates to the native filter method, if it exists.

    var count = 0;
    var users = ["Bediako", "Dave", "Loki"], c = require('collection');
    var r = c.filter(users, function(_item, _index, _collection) { return (_index === 0); });
    util.println(r); //["Bediako"]
