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


<p id="Collection_every"></p>
### every(Object collection, Function iterator, Object context)
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


<p id="Collection_forEach"></p>
### forEach(Object collection, Function iterator, Object context)
#### Return type: n/A

<p> <label class="new">Added in 2.0</label> <label class="alias"><em>alias</em> each</label>
Iterates over a collection of elements, yielding each in turn to an iterator function. The iterator is bound to the context object, if one is passed. Each invocation of iterator is called with three arguments: (item, index, collection). For JavaScript arrays this function delegates to the native forEach function.
</p>


     var users = ["Bediako", "Dave", "Loki"];
     var index = 0;
     var results = [];
 
     collection.forEach(users, function(_item, _index, _collection)
          {
               results.push('Hello, ' + _item);
          });

     => ['Hello, Bediako', 'Hello, Dave', 'Hello, Loki']


<p id="Collection_filter"></p>
### filter(Object collection, Function iterator, Object context)
#### Return type: java.util.List|Array

<p> <label class="new">Added in 2.0</label>
Looks through each value in the list, returning a collection of all the values that pass a truth test (iterator). For JavaScript arrays this function delegates to the native filter method.
</p>


     var array = [1, true, 20, 'hello'];
     var index = 0;
     var results = collection.filter(array, function(_item, _index, _collection)
          {
               if (_index % 2 === 0)
               {
                    return false;
               }
               else
               {
                    return true;
          }
     });

     => [true, 'hello']


<p id="Collection_map"></p>
### map(Object collection, Function iterator, Object context)
#### Return type: java.util.List|Array

<p> <label class="new">Added in 2.0</label>
Produces a new collection of values by mapping each value in the collection through a transformation function (iterator). For JavaScript arrays, the native map method is used. Returns a new collection of values that contains every result returned by the execution of function against every item in the collection.
</p>


     var users = ['Bediako', 'Dave', 'Loki'];
     var index = 0;
     var results = collection.map(users, function(_item, _index, _collection)
          {
               return _item + ' is the best!';
          });

     => ['Bediako is the best!', 'Dave is the best!', 'Loki is the best!']



<p id="Collection_some"></p>
### some(Object collection, Function iterator, Object context)
#### Return type: Boolean

<p> <label class="new">Added in 2.0></label> <label class="alias"><em>alias</em> any</label>
Applies an iterator truth test to each item in the collection. The iteration will stop once all the members of the collection have been visited OR if the iterator function ever returns true. Returns true if the function returned true for any item it visited.
</p>


     var array = [1, true, 20, 'hello'];
     var pass = collection.some(array, function(_item, _index, _collection)
         {
             return ("hello".equalsIgnoreCase(_item) === true);
         });
     _assert.eq(true, pass, 'failed');

     => true


<p id="Collection_split"></p>
### split(Object collection, Function iterator, Object context)
#### Return type: Object

<p> <label class="new">Added in 2.0></label>
Returns an object with two array collections, success and fail.  The first collection, success, contains the items for which \_function returned true. The second collection, fail, contains the items for which the function returned false.
</p>


     var array = [1, true, 20, 'hello'];
     var index = 0;
     var result = collection.split(array, function(_item, _index, _collection)
          {
               if (_index % 2 === 0)
               {
                    return false;
               }
               else
               {
		    return true;
               }
	});

     => result.success: [true, 'hello']
     => result.fail: [1, 20]


<p id="Collection_partition"></p>
### partition(Object collection, String attributeName)
#### Return type: Object

<p> <label class="new">Added in 2.0</label>
Returns an object containing a value list (java.util.List or Javascript array) and a map (java.util.Map or Javascript object).  The value list is stored in property 'keys' and contains, in the order they were discovered, the set of values that each item in the collection had on its property, attribute.  The map is stored in property 'partition.' The map's keys are the values found in the value list.  Each key points to the list of items that had that value on its property identified by attributeName.
</p>

     var array = [];	
     array.push({name: 'Bediako'});
     array.push({name: 'Loki'});
     array.push({name: 'Connor'});
     array.push({name: 'Bediako'});

     var partition = collection.partition(array, 'name');

     => ['Bediako', 'Loki', 'Connor']


<p id="Collection_reduce"></p>
### reduce(Object collection, Function iterator, Object initialValue, Object context)
#### Return type: Object

<p> <label class="new">Added in 2.0</label>
Reduce boils down a collection of values into a single value. 'initialValue' is the initial state of the reduction, and each successive step of it should be returned by iterator. Reduce defers to the native implementation for JavaScript arrays.
</p>


     var array = [1, true, 20, 'hello'];
     var result = collection.reduce(array, function(_result, _item, _index, _collection)
         {
             return _result + '' + _item;
         }, '');

     => '1true20hello'

     var set = new java.util.HashSet();
     set.add(1);
     set.add(2);
     set.add(3);
     set.add(4);
     var result = collection.reduce(set, function(_result, _item, _index, _collection)
         {
             return _result + _item.intValue();
         }, 0);

     => 10
