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


The following table describes the properties of the Javascript Object returned by the previous code. It returns a property of the resource if it has a value for that property. If not, returns a default value. The returned properties are Java HashSets of roles that can make requests to the resource.

<br>

<table class="functions">
  <tr>
    <th class="head">Property</th>
    <th class="head">Description</th>
  </tr>
  <tr class="even">
    <th id="ResourceSecurityMetadata_collectRoles">collectRoles</th>
    <td>Returns a HashSet of the roles that can collect this resource, or {'all': 1}.</td>
  </tr>
  <tr class="odd">
    <th id="ResourceSecurityMetadata_putRoles">putRoles</th>
    <td>Returns a HashSet of the roles that can update this resource, or {'all': 1}.</td>
  </tr>
  <tr class="even">
    <th id="ResourceSecurityMetadata_postRoles">postRoles</th>
    <td>Returns a HashSet of the roles that can create this resource, or {'all': 1}.</td>
  </tr>
  <tr class="odd">
    <th id="ResourceSecurityMetadata_headRoles">headRoles</th>
    <td>Returns a HashSet of the roles that can get this resource, or {'all': 1}.</td>
  </tr>
  <tr class="even">
    <th id="ResourceSecurityMetadata_getRoles">getRoles</th>
    <td>Returns a HashSet of the roles that can get this resource, or {'all': 1}.</td>
  </tr>
  <tr class="odd">
    <th id="ResourceSecurityMetadata_deleteRoles">deleteRoles</th>
    <td>Returns a HashSet of the roles that can delete this resource, or {'noone': 1}.</td>
  </tr>
</table>

<br>


     resourceSecurityMetadata.collectRoles;       => {'manager': 1, 'employee': 1}
     resourceSecurityMetadata.putRoles;           => {'manager': 1}
     resourceSecurityMetadata.deleteRoles;        => {'noone': 1}






