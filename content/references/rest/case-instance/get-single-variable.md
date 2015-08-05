---

title: "Get Single Case Instance Variable"
weight: 90

menu:
  main:
    identifier: "rest-api-case-instance-get-single-variable"
    parent: "rest-api-case-instance"

---


Retrieves a variable of a given case instance.


Method
------

GET `/case-instance/{id}/variables/{varId}`


Parameters
----------

#### Path Parameters

<table class="table table-striped">
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>id</td>
    <td>The id of the case instance to retrieve the variable from.</td>
  </tr>
  <tr>
    <td>varId</td>
    <td>The name of the variable to get.</td>
  </tr>
</table>

#### Query Parameters

<table class="table table-striped">
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>deserializeValue</td>
    <td>
      <%- @partial('api-references/rest/variables/variable-query-param-deserialize-object-value.html.md', @, {}) %>
    </td>
  </tr>
</table>



Result
------

A JSON object with the following properties:

<%- @partial('api-references/rest/variables/variable-response.html.md.eco', @, {deserializationParameter: 'deserializeValue'}) %>


Response codes
--------------

<table class="table table-striped">
  <tr>
    <th>Code</th>
    <th>Media type</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>200</td>
    <td>application/json</td>
    <td>Request successful.</td>
  </tr>
  <tr>
    <td>404</td>
    <td>application/json</td>
    <td>Variable with given id does not exist. See the <a href="ref:#overview-introduction">Introduction</a> for the error response format.</td>
  </tr>
</table>

Example 1
---------

#### Request

GET `/case-instance/aCaseInstanceId/variables/aVarName`

#### Response

<%- @partial('api-references/rest/variables/variable-response-example-deserialized.html.md', @, {}) %>

Example 2
---------

#### Request

GET `/case-instance/aCaseInstanceId/variables/aVarName?deserializeValue=false`

#### Response

<%- @partial('api-references/rest/variables/variable-response-example-serialized.html.md', @, {}) %>