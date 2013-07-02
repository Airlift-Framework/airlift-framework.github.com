---
layout: null
published: true
title: Collection
abstract: The Collection module contains functions that can be used to traverse and process JavaScript arrays and Java collections in the same manner.
author: Bediako George, Serena Lei
categories: api
---

The Collection module contains handy functions developers can use to traverse a JavaScript array, or a Java ArrayList or Java Set in a similar manner. Each function takes three parameters: collection, function, and context.

The collection parameter can be a java.util.Collection, a java.lang.String, a Javascript array, or a Javascript string to iterate over. The given function will be applied to every member of that collection or array, or every character of the java.lang.String or Javascript string. The function can expect the item/character, index, and collection/string to be passed to it at runtime.
These functions can be used by including the following code:

     var collection = require('airlift/collection');


<p id="every"></p>
### every(collection, function, \[context\])
#### Return type: Boolean

<p> <label class="new">Added in 2.0</label>
Returns true if all of the values in the list pass the iterator truth test. For JavaScript arrays, this function delegates to the native every function. The iteration stops once all the members of the collection have been visited or if the function ever returns false.
</p>


     var users = ['Bediako', 'Dave', 'Loki'];
     var success = collection.every(users, function(_item, _index, _collection)
          {
               return true;
          })

     => true


## - ForEach (collection, iterator, \[context\]) ... alias Each
Iterates over a collection of elements, yielding each in turn to an iterator function. The iterator is bound to the context object, if one is passed. Each invocation of iterator is called with three arguments: (item, index, collection). For JavaScript arrays this function delegates to the native forEach function.

    var util = require('airlift/util'), count = 0;
    
    var users = ["Bediako", "Dave", "Loki"], c = require('collection');
    c.forEach(users, function(_item, _index, _collection) { count++; });
    util.println(count); //3


### each

    
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

<p id="some"></p>
### - Some (collection, iterator, \[context\]) ... alias Any
Returns true if any of the values in the collection pass the iterator's truth test. Short-circuits and stops traversing the list if a true element is found. If collection is a JavaScript array this function delegates to the native method some.

    var util = require('airlift/util');
    
    var users = ["Bediako", "Dave", "Loki"], c = require('collection');
    var r = c.some(users, function(_item, _index,_collection) { return (_index === 2); });
    util.println(r); //true
    

## - Reduce (collection, iterator, memo, \[context\])
Reduce boils down a collection of values into a single value. Memo is the initial state of the reduction, and each successive step of it should be returned by iterator. The iterator is passed four arguments: the memo, then the value and the index of the iteration, and finally a reference to the entire list.  Reduce defers to the native implementation for JavaScript arrays.

    var util = require('airlift/util');
    
    var users = ['Bediako', 'Dave', 'Loki'], c = require('collection');
    var r = c.reduce(users, function(_memo, _item, _index, _collection) { return _memo + _item.length; }, 0);
    util.println(r); //15


### any
    
## - Split (collection, iterator, \[context\])
Returns two collections.  The first collection contains the items for which \_function returned true, the second collection contains the items for which the function returned false.

    var util = require('airlift/util');
    
    var users = ["Bediako", "Dave", "Loki"], c = require('collection');
    var r = c.split(users, function(_item, _index, _collection) { return _item.length > 4; });
    util.println(util.json(r)); //{success: ["Bediako"], fail: ["Dave", "Loki"] }
    
## - Partition (collection, attributeName)
Returns a value list (java.util.List or Javascript array) and a map (java.util.Map or Javascript object).  The value list contains, in the order they were discovered, the values that each item in the collection had on its property identified by attributeName.  The map's keys are the values found in the value list.  Each key points to the list of items that had that value on its property identified by attributeName.

    var util = require('airlift/util');
    
    var users = \[{name: "Bediako"}, {name: "Dave"}, {name: "Loki"}, {name: "Bediako"}\];
    var r = require('collection').partition(users, 'name');
    util.println(util.json(r)); //{keys: \["Bediako", "Dave", "Loki"\], partition: {"Bediako" : \[{name: "Bediako"}, {name: "Bediako"}\], "Dave": \[{name: "Dave"}\], "Loki": \[{name: Loki}\]}}

### reduce
