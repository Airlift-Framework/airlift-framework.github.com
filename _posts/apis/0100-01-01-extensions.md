---
layout: api
title: Extensions
abstract: The resource module contains functions that allow you to iterate over the attributes of your application's resources.
author: Bediako George
categories:
- apis
published: true
---

# Introduction
Airlift is a restful framework.  Resources are the center of Airlift application development.  When designing an application, developers are encouraged to create as many resources as they like.  The resource.js module contains functions that allow developers to traverse the application resources' attributes.  In Airlift a resource is represented as a simple JavaScript object ({}).

Whenever a iterative function is executed in resource, the iterator function that you provide is executed within a context that governs the traversal of that resource.  This context is set as the 'this' for the iterator function.  It makes available following:

* resourceName - the name of the resource being traversed.
* resourceMetadata - metadata describing the resource being traversed.  It contains a list of attributes this resource holds.
* attributesMetadata - metadata describing each individual attribute this resource holds.
* foreignKeys - a list of names of all the foreign keys in this resource.
* attributes - a list of names of all the attributes in this resource.
* web - a web object that gives access to the web context.  The web context contains information about the current request.
* report - a function used to report errors.
* allErrors - a function that returns all errors reported so far.
* getErrors - a function that returns all errors reported for a given attribute of this resource.

All iterative functions in resource.js allow for the replacement of any of the attributes of the context object by optionally providing an object at invocation time.

The functions available in this module are described below.

## - Each (resourceName, resource, iterator, \[context\])
Iterates over a resource, yielding each in turn to an iterator function. The iterator is bound to the context object, if one is passed, along with the attributes provided in the default context. Each invocation of iterator is called with four arguments: (value, attributeName, resource, metadata).

    var person = {fullName: 'Kwame Mtume', shortName: 'Kwame', age: 27};
    var lightPerson = {};
    var res = require('resource');
    var context = {attributes: ['shortName', 'age']}; //optional - set to limit iteration
    
    res.each('person', person, function(_value, _name, _resource, _metadata)
    {
       lightPerson[_name] = _value;
    } , context);
	
    util.println(JSON.stringify(lightPerson)); // {shortName: 'Kwame', age: 27 }

## - Map (resourceName, resource, iterator, \[context\])
Iterates over a resource, yielding each in turn to an iterator function. The iterator is bound to the context object, if one is passed, along with the attributes provided in the default context. Each invocation of iterator is called with four arguments: (value, attributeName, resource, metadata).  The result of each iterator invocation is saved to a new resource object.

    var person = {fullName: 'Kwame Mtume', shortName: 'Kwame', age: 27};
    var res = require('resource');
    var context = {attributes: ['shortName', 'age']}; //optional - set to limit iteration
    
    var lightPerson = res.map('person', person, function(_value, _name, _resource, _metadata)
    {
       return _value;
    } , context);
    
    util.println(JSON.stringify(lightPerson)); // {shortName: 'Kwame', age: 27 }

## - Reduce (base, resourceName, resource, iterator, \[context\])
Iterates over a resource, yielding each in turn to an iterator function. The iterator is bound to the context object, if one is passed, along with the attributes provided in the default context. Each invocation of iterator is called with five arguments: (base, value, attributeName, resource, metadata).  The result of each iterator invocation replaces the base value.  Reduce returns the value of base at the end.

    var person = {fullName: 'Kwame Mtume', shortName: 'Kwame', age: 27};
    var res = require('resource');
    var context = {attributes: ['shortName', 'age']}; //optional - set to limit iteration
    var base = '<ul>';
    
    var lightPerson = res.reduce(base, 'person', person, function(_value, _name, _resource, _metadata)
    {
       return '<li>' + _value + '</li>';
    } , context);
    
    util.println(lightPerson); // <ul><li>Kwame</li><li>27</li>
    
## - Sequence (function1, function2, ..., functionN)
Returns a function that is the composition of the passed function arguments.  The functions are executed in the order they are passed into sequence.  Sequence's returned function can be used in a iterative manner on a resource or executed as a standalone.  Sequence returns the value of the last function's execution. 

    var person = {fullName: 'Kwame Mtume', shortName: 'Kwame', age: 27};
    var res = require('resource');
    
    var checkStringType = function(_value, _name, _resource, _metadata) {
       if ("java.lang.String".equals(_metadata.type) === false) throw 'error';
    }
    
    var checkAttributeHasValue = function(_value)
    {
       if (util.hasValue(_value) === false) throw 'error';
    }
    
    var sequence = res.sequence(checkStringType, checkAttributeHasValue);
    var context = {attributes: ['shortName', 'age']}; //optional - set to limit iteration
    
    var lightPerson = res.each('person', person, sequence, context);  //no errors
    
## - Compose (function1, function2, ..., functionN)
Returns a function that is the composition of the passed function arguments.  The functions are executed in the order they are passed in to Compose.  Compose's returned function can be used in a iterative manner on a resource or executed as a standalone.  On execution, the function returned by Compose passes its arguments to the first function executed.  Each function after that will get the return value of the previous function as a replacement for the first argument of the original arguments.  Compose returns the value of the last function's execution. 

    var person = {fullName: 'Kwame Mtume', shortName: 'Kwame', age: 27};
    var res = require('resource');
    
    var returnOK = function(_value, _name, _resource, _metadata) {
       return 'OK';
    }
    
    var checkOK = function(_value)
    {
       if ("OK".equals(_value) === false) throw 'error';
    }
    
    var composition = res.compose(returnOK, checkOK);
    var context = {attributes: ['shortName', 'age']}; //optional - set to limit iteration
    
    var lightPerson = res.each('person', person, composition, context);  //no errors
    
## - Watch (\[name1, ..., name2\]|\[nameList\], function)
Returns a function that will only be executed once and only once when the all the attributes in the argument list of nameList are visited by the iterative function.  If an attribute list is not passed as arguments or as an array, watch will execute once and only once all the attributes of the iterative context are visited. 

    var person = {fullName: 'Kwame Mtume', shortName: 'Kwame', age: 27};
    var res = require('resource');
    
    var closeUlTag = function(_base, _value, _attributeName, _resource, _metadata) {
       return _base + '</ul>';
    }
    
    var liTag = function(_base, _value, _attributeName, _resource, _metadata)
    {
       return _base + '<li>' + _value + '</li>';
    }
    
    var context = {attributes: ['shortName', 'age']}; //optional - set to limit iteration
    var watch1 = res.watch(closeUlTag); //watch1 will execute once and only once ... 
    var composition = res.compose(liTag, watch1);
    
    var lightPerson = res.reduce('<ul>', 'person', person, composition, context); //.. when 'shortName' and 'age' are visited at least once.
    
    util.println(lightPerson); // <ul><li>Kwame</li><li>27</li></ul>