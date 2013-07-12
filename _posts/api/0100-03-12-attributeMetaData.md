---
layout: null
published: true
title: AttributeMetadata
abstract: The AttributeMetadata module allows for retrieval and inspection of an attribute's metadata.
author: Bediako George, Serena Lei
categories: api
---

When requiring the AttributeMetadata module, a Javascript object will be populated with the attribute's metadata as properties. By accessing these properties, one can inspect the state of the attribute.


     var attributeMetadata = require('airlift/attributeMetadata');


The following table describes the properties of the Javascript Object returned by the previous code. Returns a property of the attribute if it has a value for that property. If not, returns a default value.

<br>

<table class="functions">
  <tr>
    <th class="head">Property</th>
    <th class="head">Description</th>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_name">name</th>
    <td>Returns the name of the attribute, or null.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_type">type</th>
    <td>Returns the type of the attribute, or 'java.lang.String'.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_isPresentable">isPresentable</th>
    <td>Returns the isPresentable of the attribute, or true.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_displayOrder">displayOrder</th>
    <td>Returns the displayOrder of the attribute, or 1000.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_fieldSetName">fieldSetName</th>
    <td>Returns the fieldSetNameof the attribute, or ''.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_label">label</th>
    <td>Returns the label of the attribute, or ''.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_pluralLabel">pluralLabel</th>
    <td>Returns the pluralLabel of the attribute, or ''.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_displayLength">displayLength</th>
    <td>Returns the displayLength of the attribute, or 32.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_inputType">inputType</th>
    <td>Returns the inputType of the attribute, or 'TEXT'.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_textAreaRows">textAreaRows</th>
    <td>Returns the textAreaRows of the attribute, or 5.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_textAreaColumns">textAreaColumns</th>
    <td>Returns the textAreaColumns of the attribute, or 50.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_hasFormat">hasFormat</th>
    <td>Returns the hasFormat of the attribute, or '.*'.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_readOnly">readOnly</th>
    <td>Returns the readOnly of the attribute, or false.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_allowedValues">allowedValues</th>
    <td>Returns the allowedValues of the attribute, or {}.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_dateTimePattern">dateTimePattern</th>
    <td>Returns the dateTimePattern of the attribute, or "MM-dd-yyyy".</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_delimiter">delimiter</th>
    <td>Returns the delimiter of the attribute, or ','.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_isPersistable">isPersistable</th>
    <td>Returns the isPersistable of the attribute, or true.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_maxLength">maxLength</th>
    <td>Returns the maxLength of the attribute, or 200.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_minLength">minLength</th>
    <td>Returns the minLength of the attribute, or 0.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_isSearchable">isSearchable</th>
    <td>Returns the isSearchable of the attribute, or false.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_isIndexable">isIndexable</th>
    <td>Returns the isIndexable of the attribute, or false.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_isPrimaryKey">isPrimaryKey</th>
    <td>Returns the isPrimaryKey of the attribute, or false.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_isUniqueKey">isUniqueKey</th>
    <td>Returns the isUniqueKey of the attribute, or false.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_concept">concept</th>
    <td>Returns the concept of the attribute, or ''.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_nullable">nullable</th>
    <td>Returns the nullable of the attribute, or false.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_immutable">immutable</th>
    <td>Returns the immutable of the attribute, or false.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_ranged">ranged</th>
    <td>Returns the ranged of the attribute, or false.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_minValue">minValue</th>
    <td>Returns the minValue of the attribute, or null.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_maxValue">maxValue</th>
    <td>Returns the maxValue of the attribute, or null.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_encrypted">encrypted</th>
    <td>Returns the encrypted of the attribute, or false.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_semanticType">semanticType</th>
    <td>Returns the semanticType of the attribute, or 'NONE'.</td>
  </tr>
  <tr class="odd">
    <th id="AttributeMetadata_mapTo">mapTo</th>
    <td>Returns the mapTo of the attribute, or null.</td>
  </tr>
  <tr class="even">
    <th id="AttributeMetadata_mapToMany">mapToMany</th>
    <td>Returns the mapToMany of the attribute, or null.</td>
  </tr>
</table>

<br>


     attributeMetadata.name;                 => 'ex output'
     attributeMetadata.readOnly;             => true
     attributeMetadata.encrypted;            => false

