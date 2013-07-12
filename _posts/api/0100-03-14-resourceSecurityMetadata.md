---
layout: null
published: true
title: ResourceSecurityMetadata
abstract: The ResourceSecurityMetadata module allows for retrieval and inspection of a resource's security metadata.
author: Bediako George, Serena Lei
categories: api
---

When requiring the ResourceSecurityMetadata module, a Javascript object will be populated with the resource's security metadata as properties. By accessing these properties, one can inspect the state of the resource's security.


     var resourceMetadata = require('airlift/resourceMetadata');


The following table describes the properties of the Javascript Object returned by the previous code. Returns a property of the resource if it has a value for that property. If not, returns a default value.

<br>

<table class="functions">
  <tr>
    <th class="head">Property</th>
    <th class="head">Description</th>
  </tr>
  <tr class="even">
    <th id="ResourceSecurityMetadata_collectRoles">collectRoles</th>
    <td>Returns the collectRoles of the resource's security, or {'all': 1}.</td>
  </tr>
  <tr class="odd">
    <th id="ResourceSecurityMetadata_putRoles">putRoles</th>
    <td>Returns the putRoles of the resource's security, or {'all': 1}.</td>
  </tr>
  <tr class="even">
    <th id="ResourceSecurityMetadata_postRoles">postRoles</th>
    <td>Returns the postRoles of the resource's security, or {'all': 1}.</td>
  </tr>
  <tr class="odd">
    <th id="ResourceSecurityMetadata_headRoles">headRoles</th>
    <td>Returns the headRoles of the resource's security, or {'all': 1}.</td>
  </tr>
  <tr class="even">
    <th id="ResourceSecurityMetadata_getRoles">getRoles</th>
    <td>Returns the getRoles of the resource's security, or {'all': 1}.</td>
  </tr>
  <tr class="odd">
    <th id="ResourceSecurityMetadata_deleteRoles">deleteRoles</th>
    <td>Returns the deleteRoles of the resource's security, or {'all': 1}.</td>
  </tr>
</table>

<br>


     resourceSecurityMetadata.collectRoles;       => true
     resourceSecurityMetadata.putRoles;           => false
     resourceSecurityMetadata.deleteRoles;        => true






