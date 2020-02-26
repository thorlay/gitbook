# The-HTTP-Protocol

## WWW Server

* Enables browser requests
* Mainly provides
  * Support for retrieving hypertext documents
  * Manages access to the Web site
  * Provides several mechanisms for executing server-side scripts
    * Common Gateway Interface \(CGI\)
    * Application Programmers Interface \(API\)
  * produces log files and usage statistics

## How Does a Web Server Communicate?

* Web browsers and servers communicate using the HyperText Transfer Protocol \(HTTP\)
* HTTP is a lightweight protocol
  * different from the ftp protocol
    * ftp sessions are long lived and there are two connections, one for control, one for data

## MIME MEDIA TYPES

* HTTP tags all data that it sends with its MIME type
* HTTP sends the MIME type of the file using the line Content-Type: mime type header
* For example here are 2 MIME type messages
  * Content-type: image/jpeg Content-length: 1598
* Some important MIME types are
  * – text/plain, text/html
  * image/gif, image/jpeg
  * audio/basic, audio/wav, audio/x-pn-realaudio
  * model/vrml
  * video/mpeg, video/quicktime, video/vnd.rnrealmedia, video/x-ms-wmv
  * application/\*, application-specific data that does not fall under any other MIME category, e.g. application/vnd.ms-powerpoint

## Multipurpose Internet Mail Extensions

* MIME is an Internet standard for electronic mail
  * Traditional e-mail was limited to ASCII text, limited line length, and limited size
* MIME has extended Internet e-mail to include
  * Unlimited text line and message length
  * Messages with multiple body parts or objects enclosed
  * Messages that point to files on another server and are automatically retrievable
  * International character sets in addition to US-ASCII
  * Formatted text including multiple font styles
  * Images
  * Video clips
  * Audio messages
  * Application-specific binary data
* MIME converts data that uses all eight bits into 7bit ASCII, sends it, and reconverts it at the other end
* MIME headers at the front of the file define the type of data the message includes.

  **An HTTP 1.0 “default” Scenario**

  Communication takes place over a TCP/IP connection, generally on port 80

  | Client action | Server response |
  | :---: | :---: |
  | Client opens a connection | Server responds with an acknowledgment |
  | Client sends HTTP request for HTML document | Server responds with the document and closes the connection |
  | Client parses the HTML document and opens a new connection; it sends a request for an image | Server responds with the inlined image and closes the connection |
  | Client opens a connection and sends another request for another image | Server sends the inlined image and closes the connection |

## A More Complicated HTTP Scenario

* Actually, communication between a browser and a web server can be much more complicated; communication can go between one or more intermediaries.
* There are three common forms of intermediary: proxy, gateway, and tunnel.
  * A proxy is a forwarding agent, receiving requests for a URI in its absolute form, rewriting all or part of the message, and forwarding the reformatted request toward the server identified by the URI.
  * A gateway is a receiving agent, acting as a layer above some other server\(s\) and, if necessary, translating the requests to the underlying server’s protocol.
  * A tunnel acts as a relay point between two connections without changing the messages; tunnels are used when the communication needs to pass through an intermediary \(such as a firewall\) even when the intermediary cannot understand the contents of the messages.

## Caching Proxies

* A web cache or caching proxy is a special type of HTTP proxy server that keep copies of popular documents that pass through the proxy \(“forward” proxy\). The next client requesting the same document can be served from the cache's personal copy.

## Gateways

* Gateways are special servers that act as intermediaries for other servers.
* They are often used to convert HTTP traffic to another protocol. A gateway always receives requests as if it was the origin server for the resource. The client may not be aware it is communicating with a gateway.
* For example, an HTTP/FTP gateway receives requests for FTP URIs via HTTP requests but fetches the documents using the FTP protocol. The resulting document is packed into an HTTP message and sent to the client.

## Tunnels

* Tunnels are HTTP applications that, after setup, blindly relay raw data between two connections. HTTP tunnels are often used to transport non-HTTP data over one or more HTTP connections, without looking at the data.

## Persistent Connections

* In the original HTTP protocol each request was made over a new connection
  * so an HTML page with n distinct graphic elements produced n+1 requests
* TCP uses a three-way handshake when establishing a connection, so there is significant latency in establishing a connection
  * client sends SYN, server replies ACK/SYN, client responds with ACK
* HTTP 1.0 introduced a keep-alive feature
  * the connection between client and server is maintained for a period of time allowing for multiple requests and responses
  * a.k.a. Persistent connection

## HTTP/1.0 Keep Alive Connections

| client | server |
| :--- | :--- |
| 1. Open connection | Acknowledge connection |
| Send 1st request | Receive request send response |
| Receive 1st response Send 2nd request | receive request send response |
| Receive 2nd response etc | etc |
| Close connection | Close connection |

## HTTP/1.1 Keep Alive Extensions

* Persistent connections are now the default
* Request Header to set timeout \(in sec.\) and max. amount of requests, before closing: Keep-Alive: timeout=5, max=1000
* client and server must explicitly say they do NOT want persistence using the header Connection: close
* HTTP permits multiple connections in parallel
  * client requests a page and server responds
  * client parses page and initiates 3 new connections, each requesting a different image
* Above scheme is NOT always faster, as multiple connections may compete for available bandwidth
* Generally browsers severely limit multiple connections and servers do as well

## Client HTTP Requests

* The general form of an HTTP request has four fields:
  * HTTP\_Method says what is to be done to the object specified in the URL; some possibilities include GET, HEAD, and POST
  * identifier is the URL of the resource or the body
  * HTTP\_version is the current HTTP version, e.g. HTTP/1.1
  * Body is optional text

## HTTP Authentication

* The web server can maintain secure directories and request authentication when someone tries to access them
* Procedure
  * web server receives a request without proper authorization
  * web server responds with 401 Authentication Required
  * client prompts for username and password and returns the information to the web server
  * 

