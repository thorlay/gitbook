# The Web Server

What Does the WWW Server Do?

Enables browser requests

• Mainly provides

– Support for retrieving hypertext documents

– Manages access to the Web site

– Provides several mechanisms for executing server-side scripts

•Common Gateway Interface (CGI)

•Application Program Interface (API)

•Direct Module Interfaces (SAPI)

– provides log files and usage statistics

#### What to Look for in a Web Server

• Main features

– platform they run on;

– complete support for HTTP 1.1 / HTTP 2

– Multithreading, load balancing

• Security features

– ability to provide IP address restriction

– ability to provide domain name restriction

– Support for secure transactions: SSL

– Ability to act as a proxy server

#### How Servers Handle Multiple Requests

For each request, a complete copy of the server is made and executed

– Initially a parent process waits for requests; for each new request a child process is spawned

• Or, a single server program handles many requests simultaneously (multithreaded)

– the server must keep track of all requests and switch between them as needed

– writing multithreaded programs is easier in a language that supports multiple threads, e.g. Java

### Application Web Server

An application server is software that typically interfaces one or more databases to convey processed data to and from a user interface such as a web browser

### Web Server Features

#### Document Root

The Web server has access to a tree of files that it can deliver

– the files are created by content providers

– files may contain text, images, sound, video, other programs, etc.

• the document tree is organized by the web site administrator

• The root of the document tree is given to the web server when it starts

#### Virtually Hosted Document Roots

Hosting multiple web sites by the same web server

• It uses the host name or IP address to distinguish the document roots, e.g.

GET /index.html HTTP/1.0 

Host: www.hardware.com might return documents from /htdocs/hardware, while 

GET /index.html HTTP/1.0 Host: www.antiques.com might return documents from /htdocs/antiques 

#### Directory Listing

When the URL path resolves to a directory, not to a file, a web server can be configured to return more than just a default file; to the right you see the server returning a list of files in the directory including special icons for files and folders Important Note: Turn off this feature! Remove “Indexes” from Options Indexes in httpd.conf

#### Basic User Authentication 

Basic authentication is supported by all HTTP servers

– The server administrator creates secure directories accessible via password files maintained by the server

– Client requests a resource from a secure directory; e.g., GET /secure/test.html HTTP/1.0

– Server responds with authentication request to the client; e.g., HTTP/1.0 401 Unauthorized

– Browser requests user name and password, scrambles them, and retries the request

GET http://domain/secure/test.html HTTP/1.0 Authorization: Basic 0<V%L:EB.G-E8W))$J – Server decodes name and password and checks it against its password file

#### Creating Server-Side Applications

Web Servers offer several mechanisms

– Application Programming Interface (API)

– Common Gateway Interface (CGI)

– J2EE / .NET interfaces

– Chrome V8 JavaScript Engine (Google)

• Node.js

– Direct Module Interfaces (PHP)

• Apache offers a PHP module

• Microsoft IIS server-side supports:

– CGI applications

– API applications compiled as DLL

– Active Server Pages (written in VBScript)

– ASP.NET applications (written in C++, VB.NET, C#, or HTML/CSS/JavaScript)

### Configuring a Server

No matter which operating system or server, you will need to define the

1. location of the server (server root)

2. location of documents to deliver (document root)

3. location of CGI scripts or server-side components to execute

• You may also wish to define

– Access restrictions

– Fancy indexing

– Sys admin e-mail

– Other features

## The Apache Web Server

The Apache httpd server

– is a powerful, flexible, HTTP/1.1 compliant web server

– implements the latest protocols, including HTTP/1.1 (RFC2616)

– is highly configurable and extensible with third-party modules

– can be customized by writing 'modules' using the Apache module API

– provides full source code and comes with an unrestrictive license

– runs on Windows, Netware, Mac OS X, Linux, and most versions of Unix, as well as several other operating systems