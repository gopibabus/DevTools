# 🔥HTTP Status Codes & Methods

## ⚡HTTP Methods
<img src="./assets/images/http_methods.jpg" alt="http methods" width="700" height="350">

| HTTP Method | Meaning        | Purpose                                                                         |
| ----------- | -------------- | ------------------------------------------------------------------------------- |
| **GET**     | Read           | Requests a representation of  the specified resource                            |
| **HEAD**    | Read           | Requests for a response like GET but without response body                      |
| **OPTIONS** | Read           | Used to describe the communication options for the target resource.             |
| **POST**    | Create         | Used to submit an entity to the specified resource.                             |
| **PUT**     | Update/Replace | Replace all current representations of the target resource with request payload |
| **PATCH**   | Update/Replace | Used to apply partial modifications of the resource.                            |
| **DELETE**  | Delete         | Deletes specified resource.                                                     |

> [🌐 Reference](https://www.restapitutorial.com/lessons/httpmethods.html)

> [🌐 Reference](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)

## ⚡HTTP Status Codes
<img src="./assets/images/http_status.png" alt="http status" width="700">

?>**HTTP response status codes** indicate whether a specific HTTP request has been successfully completed. Responses are grouped into **5 classes**.

1. Informational Responses(100 - 199)
2. Successful Responses(200 - 299)
3. Redirects (300 - 399)
4. Client Responses (400 - 499)
5. Server Errors(500 - 599)

?> HTTP Status Codes that we use in RESTful web services in day to day life.

| Status Code | Meaning               | Purpose                                                                                                                          |
| ----------- | --------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| **200**     | OK                    | User request has succeeded.                                                                                                      |
| **201**     | Created               | User request has succeeded and a new resource has been created as a result.                                                      |
| **204**     | No Content            | There is no content to send from server for the user request                                                                     |
| **301**     | Moved Permanently     | The URL of the requested resource has been changed permanently. The new URL is given in the response.                            |
| **304**     | Not Modified          | This is used for caching purposes. It tells the client that the response has not been modified.                                  |
| **400**     | Bad Request           | HTTP request that was sent to the server has invalid syntax.                                                                     |
| **401**     | Unauthorized          | User trying to access the resource has not been authenticated.                                                                   |
| **403**     | Forbidden             | User made a valid request but the server is refusing to serve the request                                                        |
| **404**     | Not Found             | User is able to communicate with the server but it is unable to locate the requested file or resource                            |
| **500**     | Internal Server Error | Server cannot process the request for an unknown reason.                                                                         |
| **502**     | Bad Gateway           | Server is a gateway or proxy server, and it is not receiving a valid response from the backend servers                           |
| **503**     | Service Unavailable   | Server is overloaded or under maintenance.                                                                                       |
| **504**     | Gateway Timeout       | Server is a gateway or proxy server, and it is not receiving a response from the backend servers within the allowed time period. |

> [🌐 Reference](https://www.restapitutorial.com/httpstatuscodes.html)

> [🌐 Reference](https://www.digitalocean.com/community/tutorials/how-to-troubleshoot-common-http-error-codes)
