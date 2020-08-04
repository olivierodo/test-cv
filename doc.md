## Modules

<dl>
<dt><a href="#Given
  (Request)module_">Given
  (Request)</a></dt>
<dd></dd>
<dt><a href="#When
  (Trigger)module_">When
  (Trigger)</a></dt>
<dd></dd>
<dt><a href="#Then
  (Response)module_">Then
  (Response)</a></dt>
<dd></dd>
</dl>

<a name="Given
  (Request)module_"></a>

## Given
  (Request)

* [Given
  (Request)](#Given
  (Request)module_)
    * [~gateway()](#Given
  (Request)module_..gateway)
    * [~path()](#Given
  (Request)module_..path)
    * [~method()](#Given
  (Request)module_..method)
    * [~methodPath()](#Given
  (Request)module_..methodPath)
    * [~header()](#Given
  (Request)module_..header)
    * [~headers()](#Given
  (Request)module_..headers)
    * [~queryString()](#Given
  (Request)module_..queryString)
    * [~queriesString()](#Given
  (Request)module_..queriesString)
    * [~JsonPayload()](#Given
  (Request)module_..JsonPayload)
    * [~JsonPayloadNull()](#Given
  (Request)module_..JsonPayloadNull)
    * [~JsonPayloadTrue()](#Given
  (Request)module_..JsonPayloadTrue)
    * [~JsonPayloadFalse()](#Given
  (Request)module_..JsonPayloadFalse)
    * [~JsonPayloadEmptyArray()](#Given
  (Request)module_..JsonPayloadEmptyArray)
    * [~JsonPayloadTable()](#Given
  (Request)module_..JsonPayloadTable)

<a name="Given
  (Request)module_..gateway"></a>

### Given
  (Request)~gateway()
### Given I have the api gateway
Define the api gateway host take a look at the config file.

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example**  
```js
Given I have the api gateway
```
**Example**  
```js
If you want to use a specific host you can use
Given I have the api gateway hosted on "https://api.example.com"
```
<a name="Given
  (Request)module_..path"></a>

### Given
  (Request)~path()
### Given I have the path {string}
Define the request path
placeholder can be used within the path for dynamic call (ex: /users/{{userid}})

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example**  
```js
Given I have the path "/users/1"
Given I have the path "/users/1/addresses"
Given I have the path "/users/{{ userId }}/addresses"
```
<a name="Given
  (Request)module_..method"></a>

### Given
  (Request)~method()
### Given I have the method {string}
Define the request method (default GET)
Available : GET, POST, PATCH, PUT, DELETE, OPTIONS, HEAD

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example**  
```js
Given I have the method "PATCH"
```
<a name="Given
  (Request)module_..methodPath"></a>

### Given
  (Request)~methodPath()
### Given I send a {string} request to {string}
Construct a request to a resource using an HTTP method

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example**  
```js
Given I send a "GET" request to "/customers"
Given I send a "POST" request to "/customers"
Given I send a "PUT" request to "/customers/1234"
Given I send a "DELETE" request to "/customers/1234"
```
<a name="Given
  (Request)module_..header"></a>

### Given
  (Request)~header()
### Given the header contains {string} as {string}
Set one request header

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example**  
```js
Given the header contains "Content-Type" as "application/json"
Given the header contains "Accept-language" as "en"
Given the header contains "user-agent" as "curl"
```
**Example** *(Placeholder from datasets)*  
```js
Given the header contains "Accept-language" as {{ language }}
Given the header contains "user-agent" as {{ currentUserAgent }}
```
<a name="Given
  (Request)module_..headers"></a>

### Given
  (Request)~headers()
### Given I add the headers:
Set one or more request headers in a single step.

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example**  
```js
Given I add the headers:
  | Content-Type     | application/json |
  | Accept-Language  | en               |
```
**Example** *(Placeholder from datasets)*  
```js
Given I add the headers:
  | Content-Type     | {{contentType}} |
  | Accept-Language  | {{ language }}  |
```
<a name="Given
  (Request)module_..queryString"></a>

### Given
  (Request)~queryString()
### Given the query parameter contains {string} as {string}
Set one or more request query parameters (example: /pets?price=10&name=john)

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example** *(string)*  
```js
Given the query parameter contains "sort" as "price"
Given the query parameter contains "name" as "john"
```
**Example** *(number)*  
```js
Given the query parameter contains "limit" as 10
Given the query parameter contains "offset" as 30
```
**Example** *(Placeholder from datasets)*  
```js
Given the query parameter contains "sort" as {{ price }}
Given the query parameter contains "name" as {{ name }}
```
<a name="Given
  (Request)module_..queriesString"></a>

### Given
  (Request)~queriesString()
### Given I add the query string parameters:
Set one or more request query parameter in a single step.

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example**  
```js
Given I add the query string parameters:
  | sort     | price |
  | name     | john  |
```
**Example** *(Placeholder from datasets)*  
```js
Given I add the query string parameters:
  | sort     | {{ sort }} |
  | name     | {{ name }}  |
```
<a name="Given
  (Request)module_..JsonPayload"></a>

### Given
  (Request)~JsonPayload()
### Given the payload contains {string} as {string | int | float | placeholder | data}
Set one or more request json body (support dot-object or jsonpath property)

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example** *(string)*  
```js
Given the payload contains "firstname" as "john"
Given the payload contains "lastname" as "doe"
Given the payload contains "people.lastname" as "doe"
```
**Example** *(int)*  
```js
Given the paylaod contains "limit" as 10
Given the paylaod contains "offset" as 30
Given the paylaod contains "page.offset" as 30
```
**Example** *(float)*  
```js
Given the paylaod contains "size" as 1.1
Given the paylaod contains "weight" as 1.0
Given the paylaod contains "body.weight" as 1.0
```
**Example** *(Placeholder form from datasets)*  
```js
Given the paylaod contains "sort" as {{ price }}
Given the paylaod contains "name" as {{ name }}
Given the paylaod contains "list.name" as {{ name }}
```
<a name="Given
  (Request)module_..JsonPayloadNull"></a>

### Given
  (Request)~JsonPayloadNull()
### Given the payload contains {string} as null
Set a value as null in the json request body (support dot-object or jsonpath property)

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example**  
```js
Given the payload contains "firstname" as null
Given the payload contains "user.firstname" as null
```
<a name="Given
  (Request)module_..JsonPayloadTrue"></a>

### Given
  (Request)~JsonPayloadTrue()
### Given the payload contains {string} as true
Set a value as true in the json request body (support dot-object or jsonpath property)

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example**  
```js
Given the payload contains "active" as true
Given the payload contains "user.active" as true
```
<a name="Given
  (Request)module_..JsonPayloadFalse"></a>

### Given
  (Request)~JsonPayloadFalse()
### Given the payload contains {string} as false
Set a value as false in the json request body (support dot-object or jsonpath property)

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example**  
```js
Given the payload contains "active" as false
Given the payload contains "user.active" as false
```
<a name="Given
  (Request)module_..JsonPayloadEmptyArray"></a>

### Given
  (Request)~JsonPayloadEmptyArray()
### Given the payload contains {string} as empty array
Set a value as empty array in the json request body (support dot-object or jsonpath property)

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example**  
```js
Given the payload contains "list" as empty array
Given the payload contains "user.list" as empty array
```
<a name="Given
  (Request)module_..JsonPayloadTable"></a>

### Given
  (Request)~JsonPayloadTable()
### Given I add the request body:
Set one or more request body information in a single step.

**Kind**: inner method of [<code>Given
  (Request)</code>](#Given
  (Request)module_)  
**Example**  
```js
Given I add the request body:
  | firstname | john |
  | lastname  | doe  |
```
**Example** *(Placeholder from datasets)*  
```js
Given I add the request body:
  | firstname    | {{ firstName }} |
  | lastname     | {{ lastName }}  |
```
<a name="When
  (Trigger)module_"></a>

## When
  (Trigger)
<a name="When
  (Trigger)module_..callApi"></a>

### When
  (Trigger)~callApi()
### When I run the API
Trigger the api call

**Kind**: inner method of [<code>When
  (Trigger)</code>](#When
  (Trigger)module_)  
**Example**  
```js
When I run the API
```
<a name="Then
  (Response)module_"></a>

## Then
  (Response)
<a name="Then
  (Response)module_..header"></a>

### Then
  (Response)~header()
### Given I set the variables:
Set variable key/value pairs which will be automatically be substitued before
sending requests.

**Kind**: inner method of [<code>Then
  (Response)</code>](#Then
  (Response)module_)  
**Example**  
```js
Given I set the variables:
| base | https://petstore.com |
| name | Fido                 |
```
