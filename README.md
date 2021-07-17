# Learn about APIs

<!-- pagebreak -->


## 1.Authentication
 - **Cookie based** Client send (POST:user/password)  Request to Server , Server create set:cookie session, next sessions client send cookie session to Server (Server check in db for cookie) sends response with the corresponding state!
![alt text](https://miro.medium.com/max/4800/1*Hg1gUTXN5E3Nrku0jWCRow.png)`

- **Token authentication** client send (POST:user/password) request to Server, Sever create token (jwt) send token to Client save token (usually in local storage), next session client send authenticate req with jwt in header (bearer:..jwt..) request to Server and Server validate token sends response with the corresponding state! 
  
    <!-- pagebreak -->
![alt text](https://miro.medium.com/max/4800/1*PDry-Wb8JRquwnikIbJOJQ.png)

- **Basic authentication** client send (POST:user/password) request to Server, Server encoded with Base64.
 **NOTED:** _Because base64 is easily decoded, Basic authentication should only be used together with other security mechanisms such as HTTPS/SSL._ 

![alt text](https://cdn-anlbg.nitrocdn.com/dKKErbUyoNysjatCgltCzbTJJilTMwLi/assets/static/optimized/rev-707c49b/wp-content/uploads/sites/1/nggallery/postman/thumbs/thumbs_Encoded_Basic_Base64-1.png)

- **Oauth** when login App Client (appid, secret, permission) send request **Auth Server** response to **Client** access token and App Client request access token to **Authorization Server** response with44 the corresponding state! 

![alt text](https://miro.medium.com/max/1400/1*aDAjqHOrsVrMnorl0MJ4LA.png)

- **Json Web Token** base64 encoded JSON object **header**, base64 encoded json **payload** object and base64 encoded URI **Signature** .
![alt text](https://topdev.vn/blog/wp-content/uploads/2017/12/jwt-la-gi.png)

_Using JWT for API authentication_ Client send (POST:user/password) request to Server create JWT with a secret return to Client save local storage,... , Client send jwt on the authorization header to Server validate sends response with the corresponding state

![alt text](https://techmaster.vn/media/fileman/Uploads/users/2504/jwt-diagram.png)

- **OpenID**
    ![alt text](https://help.tableau.com/current/server/en-us/Img/openid_auth_overview.png)
- **SAML** 
![alt text](https://doubleoctopus.com/wp-content/uploads/2018/06/Saml-Authentication-Final.png)

## 2.Open API Spec and Swagger

    OpenAPI = Specification
    Swagger = Tools for implementing the specification
 - **OpenAPI Specification** (formerly Swagger Specification) is an API description format for REST APIs. An OpenAPI file allows you to describe your entire API, including:
 
    Available endpoints (/users)  and operations on each endpoint (GET /users, POST /users)
    Operation parameters Input and output for each operation
    Authentication methods
    Contact information, license, terms of use and other information.

API specifications can be written in YAML or JSON. The format is easy to learn and readable to both humans and machines. The complete OpenAPI Specification can be found on GitHub: OpenAPI 3.0 Specification

![alt text](https://freecontent.manning.com/wp-content/uploads/getting-to-know-openapi-definitions_01.jpg)

    Figure 1. Mental model of Swagger showing where definitions fit.

<!-- pagebreak -->

 ![alt text](https://freecontent.manning.com/wp-content/uploads/getting-to-know-openapi-definitions_02.png "width:50%")

                    Figure 2. Where we are


## 3. JSON APIs

 - **JSON:API** is a specification for how a client should request that resources be fetched or modified, and how a server should respond to those requests.

 - **JSON:API** is designed to minimize both the number of requests and the amount of data transmitted between clients and servers. This efficiency is achieved without compromising readability, flexibility, or discoverability.

 - **JSON:API** requires use of the JSON:API media type (application/vnd.api+json) for exchanging data.

    Example a GET request to an individual article could return:

```json

HTTP/1.1 200 OK
Content-Type: application/vnd.api+json

{
  "links": {
    "self": "http://example.com/articles/1"
  },
  "data": {
    "type": "articles",
    "id": "1",
    "attributes": {
      "title": "JSON:API paints my bikeshed!"
    },
    "relationships": {
      "author": {
        "links": {
          "related": "http://example.com/articles/1/author"
        }
      }
    }
  }
}
```
    if the above article’s author is missing, 
    then a GET request to that related resource would return:
```json
HTTP/1.1 200 OK
Content-Type: application/vnd.api+json

{
  "links": {
    "self": "http://example.com/articles/1/author"
  },
  "data": null
}
```

## 4. SOAP 

 - **SOAP** (Simple Object Access Protocol) is a standard protocol defined by the W3C standards for sending and receiving web service requests and responses. 

      Workflow for the SOAP API services run

![alt text](https://www.sparsh-technologies.com/images/blogs/detail/magento-2-soap-api4.jpg)


## 5. REST API

 - **REST** is short for Representational State Transfer, an architectural style for building web services that interact via an HTTP protocol. Its principles were formulated in 2000 by computer scientist Roy Fielding and gained popularity as a scalable and flexible alternative to older methods of machine-to-machine communication. It still remains the gold standard for public APIs.

![alt text](https://content.altexsoft.com/media/2021/03/word-image.png)

The key elements of the REST API paradigm are

    a client or software that runs on a user’s computer or smartphone and initiates communication;
    a server that offers an API as a means of access to its data or features; and
    a resource, which is any piece of content that the server can provide to the client (for example, a video or a text file).

REST request structure
- HTTP method 
- Headers
- Body

        POST to Create a resource,
        GET to Retrieve a resource,
        PUT to Update a resource, and
        DELETE to Delete a resource.

![alt text](https://content.altexsoft.com/media/2021/03/word-image-1.png)

        REST request for creating a new user where the response will return the ID of the created resource. Source: Tableau API



<!-- # This is a Header

## This is a Smaller Header

### This is an Even Smaller Header

Here is some normal text. A paragraph, even!

_This text is in italics._

**This text is in bold.**

**_This text is in both._**

~~This text is rendered with a strikethrough.~~

- Item
- Item
- Another item

1. Item one
2. Item two
3. Item three

1. Item one
2. Item two
3. Item three 
    1. Sub-item 
    2. Sub-item
4. Item four

---

[I'm a link to a web page!](http://www.google.com)
![alt text](https://i.imgur.com/81qyN1y.jpg)` -->

