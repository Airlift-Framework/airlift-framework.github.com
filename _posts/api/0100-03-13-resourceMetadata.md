---
layout: null
published: true
title: ResourceMetadata
abstract: The ResourceMetadata module allows for retrieval and inspection of a resource's metadata.
author: Bediako George, Serena Lei
categories: api
---

When requiring the ResourceMetadata module, a Javascript object will be populated with the resource's metadata as properties. By accessing these properties, one can inspect the state of the resource.


     var resourceMetadata = require('airlift/resourceMetadata');


The following table describes the properties of the Javascript Object returned by the previous code. Returns a property of the resource if it has a value for that property. If not, returns a default value.

<br>

<table class="functions">
  <tr>
    <th class="head">Property</th>
    <th class="head">Description</th>
  </tr>
  <tr class="even">
    <th id="ResourceMetadata_isView">isView</th>
    <td>Returns a boolean of whether or not the attribute is a view, or false.</td>
  </tr>
  <tr class="odd">
    <th id="ResourceMetadata_isPresented">isPresented</th>
    <td>Returns a boolean of whether or not the attribute is presented, or true.</td>
  </tr>
  <tr class="even">
    <th id="ResourceMetadata_isPersisted">isPersisted</th>
    <td>Returns a boolean of whether or not the attribute is persisted, or true.</td>
  </tr>
  <tr class="odd">
    <th id="ResourceMetadata_isCached">isCached</th>
    <td>Returns a boolean of whether or not the attribute is cached, or true.</td>
  </tr>
  <tr class="even">
    <th id="ResourceMetadata_isSecured">isSecured</th>
    <td>Returns a boolean of whether or not the attribute is secured, or true.</td>
  </tr>
  <tr class="odd">
    <th id="ResourceMetadata_isAudited">isAudited</th>
    <td>Returns a boolean of whether or not the attribute is audited, or false.</td>
  </tr>
  <tr class="even">
    <th id="ResourceMetadata_lookingAt">lookingAt</th>
    <td>Returns an object of what the attribute is currently looking at, or undefined.</td>
  </tr>
</table>

<br>


     resourceMetadata.isView;                => true
     resourceMetadata.isCached;              => false
     resourceMetadata.lookingAt;             => true






