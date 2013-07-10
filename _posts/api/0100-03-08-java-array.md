---
layout: null
published: true
title: JavaArray
abstract: The Java Array module provides functions for creating Java arrays of various generics.
author: Bediako George, Serena Lei
categories: api
---

The following functions will initialize a Java array, copying over Javascript array elements if given.


     var javaArray = require('airlift/javaArray');


<p id="JavaArray_createArray"></p>
### createArray(Number size, Class type, Array initializer)
#### Return type: java.lang.Object

<p> <label class="new">Added in 2.0</label>
Creates a Java array of the specified size and type. If an initialization array is provided, the contents of that array are copied to the Java array. 'size' is the initial size of the array and defaults to 0. 'type' is the Java type of the array and defults to java.lang.String. 'initializer' is an array of values that should be copied to the array and defaults to an empty array.
</p>


     var stringArray = javaArray.createArray(3, java.lang.String, ["Bediako", "Loki"]);
     java.util.Arrays.toString(stringArray);
     => '[Bediako, Loki, null]'

     stringArray.getClass();
     => [Ljava.lang.String;


The following functions also serve to initialize Java arrays.  Each function requires two parameters, Number size and Array initializer.  The functions call this module's createArray function, passing the two parameters as well as the appropriate Class type.

<br>
<br>

<table class="functions">
  <tr>
    <th>Function(Number size, Array initializer)</th>
    <td>Description</td>
  </tr>
  <tr>
    <th>stringArray</th>
    <td>Returns a Java string array.</td>
  </tr>
  <tr>
    <th>byteArray</th>
    <td>Returns a Java byte array.</td>
  </tr>
  <tr>
    <th>byteObjectArray</th>
    <td>Returns a Java byte object array.</td>
  </tr>
  <tr>
    <th>shortArray</th>
    <td>Returns a Java short array.</td>
  </tr>
  <tr>
    <th>shortObjectArray</th>
    <td>Returns a Java short object array.</td>
  </tr>
  <tr>
    <th>charArray</th>
    <td>Returns a Java char array.</td>
  </tr>
  <tr>
    <th>characterObjectArray</th>
    <td>Returns a Java character object array.</td>
  </tr>
  <tr>
    <th>intArray</th>
    <td>Returns a Java int array.</td>
  </tr>
  <tr>
    <th>integerObjectArray</th>
    <td>Returns a Java integer array.</td>
  </tr>
  <tr>
    <th>longArray</th>
    <td>Returns a Java long array.</td>
  </tr>
  <tr>
    <th>longObjectArray</th>
    <td>Returns a Java long object array.</td>
  </tr>
  <tr>
    <th>booleanArray</th>
    <td>Returns a Java boolean array.</td>
  </tr>
  <tr>
    <th>booleanObjectArray</th>
    <td>Returns a Java boolean object array.</td>
  </tr>
  <tr>
    <th>floatArray</th>
    <td>Returns a Java float array.</td>
  </tr>
  <tr>
    <th>floatObjectArray</th>
    <td>Returns a Java float object array.</td>
  </tr>
  <tr>
    <th>doubleArray</th>
    <td>Returns a Java double array.</td>
  </tr>
  <tr>
    <th>doubleObjectArray</th>
    <td>Returns a Java double object array.</td>
  </tr>
</table>
