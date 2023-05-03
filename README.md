1. What is API? Give 3 real-life examples of usage of API.
>Ans: API is Application Programming Interface. It is a middleware connection between two application. 
API allows client application to send and receive a response with a status from server application.
Example includes, paying with PayPal for an online transaction. Client application redirected to PayPal using API to complete the transaction.
Then there is mapping API. Upon clicking on direction button from a remote device, a map opens to show client the direction path.
Finally, there are social media API's. Usually upon clicking on media icon the media sites opens using API service

2. What is API testing and name some types of API testing?
>Ans: API testing allows tester to validate whether they are receiving an expected response after sending a request from client application.
There are different types of API testing. For example, REST API, which is done using GET, POST, PUT, DELETE etc. request. It is flexible. Easy to understand and programme. 
Another type is SOAP API. Which is not very flexible. It require more overhead, and are typically used in enterprise environments where more advanced features like transaction management and security are required.

3. What is the difference between REST and SOAP APIs?
>Ans: There are some differences between REST and SOAP API's. some of them as:
a. REST normally uses easier messaging formats such as JSON or XML, 
   while SOAP uses a more complex messaging format that includes an XML, headers, and body.
b. REST API's are considered easy to understand and more flexible, and it can be easily integrated with third party web applications. 
   However, SOAP API's, can be more complex to set up and use due to their heavy use of XML.
c. REST APIs are generally faster and more scalable than SOAP APIs


4. What are common HTTP methods? Explain with examples.
>Ans: HTTP (Hypertext Transfer Protocol) or HTTPS (Hypertext Transfer Protocol Secure) to exchange data between client and server using HTTP methods – 
a. GET: GET is used to receive a response from server after sending a request from client application. 
b. POST: Using POST call user tells the server to create a new record.
c. UPDATE: Using PUT call user can update an existing record in server
d. DELETE: DELETE call is used to delete an existing record from the server.
These are the common HTTP method. There are also HEAD, PATCH, etc.

5. What is the difference between POST AND put? Explain with example.
>Ans: Using POST call user send a request to the server to create a new record. POST call may require to go through the authorization before creating a new record. 
 Ex, registering myself to the public library. 
 On the other hand, PUT call is used to update an existing record in server. 
 Ex, adding an additional cardholder to my existing credit card. 

6. Name 5 main categories of HTTP status codes? Explain 5 status codes from each category(You have to tell the status code and description of each status code with an example).
>Ans:
Informational (1xx): These status codes indicate that the server has received the request and is continuing to process it. Examples include:
100 Continue, 101 Switching Protocols. 
Success (2xx): These status codes indicate that the request was successfully received, understood, and processed by the server. Examples include:
200 OK, 201 Created.
Redirection (3xx): These status codes indicate that the requested resource has been moved or is no longer available at the original location. Examples include:
301 Moved Permanently, 304 Not Modified.
Client Error (4xx): These status codes indicate that there was an error with the request made by the client, such as an invalid URL or missing authentication. Examples include:
400 Bad Request, 403 Forbidden.
Server Error (5xx): These status codes indicate that there was an error on the server side, such as an internal server error or a service outage. Examples include:
500 Internal Server Error, 503 Service Unavailable.

7.  What are the main components of HTTP request and HTTP response?
> Ans:
HTTP Request Components:
Request Method: The HTTP method used to make the request, such as GET, POST, PUT, DELETE, etc.
Request URL: The URL of the requested resource.
Request Headers: Additional information about the request or authentication credentials.
Request Body: Optional data sent with the request, such as form data or JSON payload.
HTTP Response Components:
Status Code: The three-digit status code returned by the server to indicate the status of the requested resource, such as 200 OK, 404 Not Found, etc.
Response Headers: Additional information about the response, such as the content type, headers.
Response Body: The data returned by the server in response to the request, such as an HTML document, JSON data, or an image file.
Response Status Line: The first line of the response that contains the HTTP version, status code, and reason phrase.

8. What are the main components of the HTTP request header and response header?
>Ans:
HTTP Request Header Components:
a. Request method
b. Request URL
c. User-Agent
d. Accept
e. Authorization
f. Cookie
HTTP Response Header Components:
a. Status code
b. Content-Type
c. Cache-Control
d. Set-Cookie
e. Server

9.  What is the difference between authentication and authorization? Briefly explain common API Authentication Methods.
>Ans: Authentication is the process of verifying the identity of a user or system username and password combination or other means of user authentication such as biometrics, two-factor authentication, or OAuth.
Authorization, on the other hand, is the process of granting or denying access to specific resources or actions based on the authenticated user's permissions or privileges.
Common API Authentication Methods:
Basic Authentication: A simple authentication method that involves sending the user's credentials in plaintext in the HTTP request header.
API Keys: A form of token-based authentication that involves providing a unique API key with each request to authenticate the client.
OAuth2: A popular authentication and authorization framework that allows users to grant third-party applications access to their resources without sharing their credentials.
JSON Web Tokens (JWT): A token-based authentication method that uses digitally signed and encrypted JSON objects to securely transmit user identity information.


Part B
Tokenization is a very common API security proess and below API endpoint will allow you to know how to deal with oauth2 basic auth token. And pass it to any API which is secured by that authorization.
1. Get Token curl --location --request POST 'https://izaan-test.auth.us-east-1.amazoncognito.com/oauth2/token' \ --header 'Authorization: Basic MXU1aW80dmE5c3I0NW43OWZjZWcyZGFtamY6MXFia3RodnA3bGJjN2FhdnVoaG1mZzhmMmNyZWtvcjloMmg3YWJ1Mm9ydTFubHBqNzFmZQ==' \ --header
   'Content-Type: application/x-www-form-urlencoded' \ --data-urlencode 'scope=izaan_test/post_info' \ --data-urlencode 'grant_type=client_credentials'`
>Ans: Status 200 OK, Received the token
![img.png](img.png)

2. Know whether you are adult, minor, senior curl --location --request POST 'https://5x9m5ed0tj.execute-api.us-east-1.amazonaws.com/test/submit' \ --header 'Content-Type: application/json' \ --header 'Authorization: Bearer CognitoTokenFromCall01 \ --data-raw '{ "name" : "John", "age" : 50 }'# API_Quiz
>Ans: Status 200 OK, Message: You are an Adult
![img_1.png](img_1.png)