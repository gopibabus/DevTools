# 🔥HTTP1 vs HTTP2

<img src="./assets/images/http.webp" alt="http" height="300" width="700">

* The **Hypertext Transfer Protocol, or HTTP**, is an application protocol that has been the de facto standard for communication on the World Wide Web since its invention in 1989.
* From the release of **HTTP/1.1** in 1997 until recently, there have been few revisions to the protocol.
* In 2015, a reimagined version called **HTTP/2** came into use, which offered several methods to decrease latency, especially when dealing with mobile platforms and server-intensive graphics and videos.
* In this changing landscape, web developers can benefit from understanding the technical differences between HTTP/1.1 and HTTP/2, allowing them to make informed and efficient decisions about evolving best practices.

### ✳HTTP/1.1

* In HTTP/1.1, a client sends a text-based request to a server by calling a method like **GET** or **POST**. In response, the server sends a resource like an HTML page back to the client.
* The web browser on your computer sends an HTTP request in the form of a text-based message, similar to the one shown below:
```bash
GET /index.html HTTP/1.1
Host: www.example.com
```
* The **example.com** web server returns an HTML page to the requesting client.
* Not all of the resources are returned to the client in the first call for data. The requests and responses will go back and forth between the server and client until the web browser has received all the resources(css, js, images etc.,) necessary to render the contents of the HTML page on your screen.

### ✳HTTP/2

* **HTTP/2** began as the **SPDY** protocol, developed primarily at Google with the intention of reducing web page load latency by using techniques such as compression, multiplexing, and prioritization.
* This protocol served as a template for HTTP/2.
* From the beginning, many browsers supported this standardization effort, including Chrome, Opera, Internet Explorer, and Safari.
* From a technical point of view, one of the most significant features that distinguishes HTTP/1.1 and HTTP/2 is the binary framing layer, which can be thought of as a part of the application layer in the internet protocol stack.
* As opposed to HTTP/1.1, which keeps all requests and responses in plain text format, HTTP/2 uses the binary framing layer to encapsulate all messages in binary format, while still maintaining HTTP semantics, such as verbs, methods, and headers.

?> **HTTP/2** still uses the same URI schemes and port numbers used in HTTP/1.1 (i.e. port 80 for http URIs, and port 443 for https URIs)

## ⚡Delivery Models

<img src="./assets/images/multoplexing.png" alt="http">

### ✳HTTP/1.1
* The first response that a client receives on an HTTP **GET** request is often not the fully rendered page. Instead, it contains links to additional resources needed by the requested page.
* Because of this, the client will have to make additional requests to retrieve these resources from server.
* In HTTP/1.0, the client had to break and remake the TCP connection with every new request, a costly affair in terms of both time and resources.
* HTTP/1.1 takes care of this problem by introducing persistent connections and pipelining. With persistent connections, HTTP/1.1 assumes that a TCP connection should be kept open unless directly told to close.
* This allows the client to send multiple requests along the same connection without waiting for a response to each, greatly improving the performance of HTTP/1.1 over HTTP/1.0.
* Since **multiple data packets cannot pass each other when traveling to the same destination**, there are situations in which a request at the head of the queue that cannot retrieve its required resource will block all the requests behind it.
* **Adding separate, parallel TCP connections** could alleviate this issue, but there are limits to the number of concurrent TCP connections possible between a client and server, and each new connection requires significant resources.

### ✳HTTP/2

<img src="./assets/images/binary.png" alt="http">

* In HTTP/2, the **binary framing layer** encodes requests/responses and cuts them up into smaller packets of information, greatly increasing the flexibility of data transfer.
* HTTP/2 establishes a single connection object between the two machines.
* In HTTP/2, requests and responses can run in parallel without blocking the messages behind them. This process is called **multiplexing**.
* Multiplexing resolves the head-of-line blocking issue in HTTP/1.1 by ensuring that no message has to wait for another to finish. This also means that servers and clients can send concurrent requests and responses.
* A single TCP connection also improves the performance of the HTTPS protocol, since the client and server can reuse the same secured session for multiple requests/responses.
*  When a client sends concurrent requests to a server, it can prioritize the responses it is requesting by assigning a **weight between 1 and 256** to each stream(1 request to server). The higher number indicates higher priority.

## ⚡Buffer Overflow
In any TCP connection between two machines, both the client and the server have a certain amount of buffer space available to hold incoming requests. There are situations, however, in which a buffer is not enough.
For example, the server may be pushing a large amount of data at a pace that the client application is not able to cope with due to a limited buffer size or a lower bandwidth.
Likewise, when a client uploads a huge image or a video to a server, the server buffer may overflow, causing some additional packets to be lost.
### ✳HTTP/1.1
* In HTTP/1.1, flow control relies on the underlying TCP connection.
* When this connection initiates, both client and server establish their buffer sizes using their system default settings.
* If the receiver’s buffer is partially filled with data, it will tell the sender its receive window, i.e., the amount of available space that remains in its buffer.
* If this advertised receive window size is zero, the sender will send no more data until the client clears its internal buffer.
* Because HTTP/1.1 relies on the transport layer to avoid buffer overflow, each new TCP connection requires a separate flow control mechanism.

### ✳HTTP/2
* HTTP/2 multiplexes streams of data within a single TCP connection.
* As a result, receive windows on the level of the TCP connection are not sufficient to regulate the delivery of individual streams.
* HTTP/2 solves this problem by allowing the client and server to implement their own flow controls, rather than relying on the transport layer.
* In terms of flow control and the stream prioritization mentioned in an earlier section, HTTP/2 provides a more detailed level of control that opens up the possibility of greater optimization.

## ⚡Predicting Resource Requests
### ✳HTTP/1.1 — Resource Inlining
* In HTTP/1.1, if the developer knows in advance which additional resources the client machine will need to render the page, they can use a technique called **resource inlining **to include the required resource directly within the HTML document that the server sends in response to the initial GET request.
* A major drawback of resource inlining, then, is that the client cannot separate the resource and the document.

### ✳HTTP/2 — Server Push

<img src="./assets/images/http2push.png" alt="http">

* Since HTTP/2 enables multiple concurrent responses to a client’s initial GET request, a server can send a resource to a client along with the requested HTML page, providing the resource before the client asks for it. This process is called **server push**.
* This means that the client can decide to cache or decline the pushed resource separate from the main HTML document, fixing the major drawback of resource inlining.
* If a client needed to adjust the priority of server push, or even disable it, it could at any time send a SETTINGS frame to modify this HTTP/2 feature.
* Some web browsers cannot always cancel pushed requests, even if the client already has the resource cached.

## ⚡Compression

<img src="./assets/images/hpack.png" alt="http">

A common method of optimizing web applications is to use compression algorithms to reduce the size of HTTP messages that travel between the client and the server.
HTTP/1.1 and HTTP/2 both use this strategy.
### ✳HTTP/1.1
* Programs like **gzip** have long been used to compress the data sent in HTTP messages, especially to decrease the size of CSS and JavaScript files.
* The header component of a message, however, is always sent as plain text. Although each header is quite small, the burden of this uncompressed data weighs heavier and heavier on the connection as more requests are made.

### ✳HTTP/2
* HTTP/2 can split headers from their data, resulting in a header frame and a data frame.
* The HTTP/2-specific compression program **HPACK** can then compress this header frame. This algorithm can encode the header metadata using Huffman coding, thereby greatly decreasing its size.

?> Features such as **multiplexing, stream prioritization, flow control, server push, and compression** in HTTP/2 will affect the changing landscape of web development.

> [🌐 Reference](https://www.digitalocean.com/community/tutorials/http-1-1-vs-http-2-what-s-the-difference)

> [🌐 Reference](https://medium.com/@factoryhr/http-2-the-difference-between-http-1-1-benefits-and-how-to-use-it-38094fa0e95b)

> [🌐 Reference](https://http2.github.io/faq/)