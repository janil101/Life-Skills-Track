# Architecture of REST

## What is REST ?

* It is a Software architecture style created by Roy Fielding in  2000 to guid the design architecture for the web.
* The Full Form of REST is (REpresentational State Transfer).
* REpresntational refers to the Format like json, xml, etc.
* State refers the Data.
* Transfer refers to the data which is being transfer between parties(Client - Server).
* Rest consists of HTTP Methods, Status codes, Response Types.

## Working of REST

* The Client Send a Request to the Server in a form of an URL which contains any of the HTTP GET,POST,PUT or DELETE method and After recieving the request Server Process that request and send a response back to the client in the form of a resource like json, xml, etc.  

## HTTP Methods

### 1) GET : 

* GET is used to retrieve information and not to modify any resource state. It is also know as safe method and it should be idempotent.
* There are 3 responses codes that GET sends:
    1) If the resource is found on the server it will return an HTTP response code "200" which means OK.
    2) If the resource is not found than is will return code "404" NOT FOUND.
    3) If the request is incorrect than it will return a response code "400" BAD REQUEST.
* Example URL : http://www.godaddy.com/users/101

### 2) POST : 

* POST is used to create a new resource into the collection of resources.
* POST method are not cacheable unless uses appropriate Cache-Control or Expires header fields.
* It is neither safe nor idempotent which means calling two similar POST request will return two different resources containing the same information except the resource ids.
* There are 2 responses code that POST sends:
    1) If the resource has been created on the origin server, the response Should be code "201" Created and contains information about the status of the request and refers to the new resource and location header.
    2) If the POST method fails to provide a result in a resource than the response code would be either "200" OK or "204" No Content.
* Example URL :HTTP POST http://www.godaddy.com/users/101

### 3) PUT :

* Replace a resource with the one being sent or create a new resource if doesn't exists.
* PUT Methods are not cacheable.
* There are 2 response ccodes that PUT sends:
    1) If a new resource is created by using the PUT Method the origin server Must inform the user agent via HTTP response code "201" Created
    response.
    2) If an existing resource is updated then wither "200"
    OK or "204" No Content responce should be sent to indicate successful completion.
* Example URL : HHTP PUT http://www.godaddy.com/users/101/accounts/222

### 4) PATCH : 

* PATCH Method is used to make partial update on a resource.
* If there is only a small modification in the resource it is better to use PATCH instead of PUT Method but PATCH Method does not Support all the browsers, servers, web application frameworks.

### 5 DELETE :

* Delete Method is used to Delete the resources.
* DELETE operations are idempotent which means if we Delete a resource it will be removed from the collection of resources.
* Responses of this method are not cacheable.
* There are 4 response code that DELETE sends :
    1) If a resource is Deleted successfully than it should send a response code "200" OK.
    2) If the delete request is in queue it should send the status response code "202" Accepted.
    3) If the action has performed but the response does not include an entity it shoud send a response code "204" No Content.
    4) If we call Delete on a resource repeatedly second time it will return a response code "404" NOT FOUND because it is already removed.
* Example URl : HTTP DELETE http://www.godaddy.com/users/101/accounts/222


## Status Codes
Here "x" is refered to 0.
* ### 1xx :  Information Responses -

    * Communicates transfer protocol-level information.
    * Example : 
        * 100 - Continue
        * 101 - Switching Protocol

* ### 2xx : Successful Responses -

    * Indicates that the client’s request was accepted successfully.
    * Example : 
        * 200 - OK
        * 202 - Accepted

* ### 3xx : Redirects -

    *  Indicates that the client must take some additional action in order to complete their request.
    * Example : 
        * 300 - Multiple Choices
        * 301 - Moved Permanently

* ### 4xx : client Errors -

    * This category of error status codes points the finger at clients.
    * Example : 
        * 400 - Bad Request
        * 401 - Unauthorized

* ### 5xx : Server Errors -

    * The server takes responsibility for these error status codes.
    * Example : 
        * 502 - Bad Gateway
        * 504 - Gateway Timeout

## Constraints for REST

* ### Client Server Architecture - 
    * This means that the Client and the Server should evovle independently.
* ### Stateless - 
    * This means that the server will not store anthing about the latest HTTP request made by the Client.
* ### Cacheable - 
    * Caching improves the performance for the client-side and provide a better scope of scalability for the server-side.
* ### Layered System -
    * This means that An application architecture needs to be composed of multiple layers.
* ### Uniform Interface -
    * This means that  there should be an uniform way of interacting with a given server irrespective of device or type of application.

## References :

* Reference for Methods: https://restfulapi.net/http-methods/
* Reference for Constraints: https://restfulapi.net/rest-architectural-constraints/
* Reference for Status Code: https://restfulapi.net/http-status-codes/
* Reference for What is REST :

    * https://www.youtube.com/watch?v=ukIE6Af4v5k

    * https://www.youtube.com/watch?v=HeXQ98sogs8&t=81s