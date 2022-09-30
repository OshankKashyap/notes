# Internet

The Internet is a global network of computers connected to each other that communicate through a standardized set of protocols.

It is made up of a large number of independently operated networks and is fully distributed there is no central control.

## Transfer of Data on The Internet

Information on the internet moves from one computer to another in the form of **bits** over various mediums, including ethernet cables, fiber optic cables, and wireless signals.

The data is broken down into smaller units called **packets**.

A packet has two parts. The **header** contains information that helps the packet get to its destination, including the length of the packet, its source and destination, and a checksum value.

**Bits** can be described as an **“ON”** or **“OFF”**. 1 means ON and 0 means OFF.

**Bit Rate —** It is the number of bits that we can actually send over a given period of time. It is measured in seconds.

**Latency** **—** It is the amount of time it takes for one bit to travel from one place to another.

The packets need not follow a fixed path, the path may change. The **routers** are responsible for the transfer of packets, and it chooses the cheapest path available.

### Protocols

It is a well-known set of rules and standards used to communicate between machines.

**TCP (Transmission Control Protocol)** — The TCP protocol is responsible for the sending and receiving of data packets.

**HTTP (HyperText Transfer Protocol)** — HTTP is the standard protocol by which webpages are transferred over the internet.

**HTML (HyperText Markup Language)** — HTML is the language used to tell a web browser how to make a page look.

**SSL (Secure Socket Layer)** — The SSL protocol is used to establish a secure connection over the internet between two devices over the HTTP protocol.

## IP Addresses

Internet Protocol (IP) addresses are numbers that computers used to identify each other on the internet.

The Most Important protocol used in the computer networks is called the **IPv4** (Internet Protocol Version 4). It is of 32 bits.

<aside>
💡 The **ICANN** (Internet Corporation for Assigned Names and Numbers) department is responsible for distributing IP addresses to ensure two different systems don’t use the same address.

</aside>

## DNS (Domain Name System)

The Domain Name System is the hierarchical and decentralized naming system used to identify computers, services, and other devices on the internet.

DNS servers are connected in a distributed hierarchy and are divided into zones splitting up the responsibility for the major domains such as .org, .com, .net, etc.

---

## Cryptography

Cryptography is the method of securing a connection between two devices over the internet. It involves two methods:

1. **Encryption** — In this process, the original message is changed to some random set of characters.
2. **Decryption** — It is the process of un-scrambling the encrypted message to make it human-readable. 

---

# HTTP

HTTP stands for **“HyperText Transfer Protocol”**. It is a web-based protocol that is used to load webpages using hyperlinks. It is a **TCP/IP-**based application layer protocol.

By default, the HTTP protocol uses port number 80. Other ports can be used as well.

<aside>
💡 **TCP/IP** stands for **Transmission Control Protocol/Internet Protocol**. It is the most widely used protocol to exchange data over the web. It standardizes how a client and a server should talk to each other. By default, the TCP/IP protocol uses port number 80.

</aside>

---

## HTTP Requests

HTTP requests are a way by which web browsers ask for the information to load a webpage. A typical HTTP request contains:

1. HTTP version
2. URL
3. HTTP method
4. HTTP request headers

The HTTP protocol sends the data in an unencrypted manner so it is very easy to read the data. As an alternative **HTTPS** is used to send data in an encrypted manner. HTTPS stands for **“HyperText Transfer Protocol Secure”**.

This protocol uses **SSL** (Secure Sockets Layer) and **TLS** (Transport Layer Security).

### HTTP Headers

A **request header** is an HTTP header that can be used in an HTTP request to provide information about the request context so that the server can tailor the response.

The header is placed before the payload and contains information such as source and destination address.

![Untitled](Internet%20894cc7682445442e95c99adb26fb24f8/Untitled.png)

The screenshot above shows the information inside an HTML request header.

### HTTP Status Code

It is a 3-digit code used to indicate whether an HTTP request has been successfully made. The main types of HTTP request codes are:

1. 200 — OK
2. 201 — OK created
3. 301 — Moved to a new URL
4. 400 — Bad request
5. 404 — Webpage not found
6. 500 — Internal server error

---

## HTTP Response Header

An HTTP response header is a component of a network packet that is sent by a web server to a web browser in response to an HTTP request.

An HTTP response header conveys important information such as the language and format of the data being sent in the response body. A typical HTTP response contains:

1. HTTP status code
2. HTTP response headers

---

### HTTP Methods

HTTP defines a set of request methods to indicate the desired action to be performed for a given resource. It involves the following methods:

1. **GET** → This method is used to retrieve data from the server.
2. **POST** → This method is used to submit data to the server.
3. **PUT** → This method is used to update data already on the server.
4. **DELETE** → This method is used to delete data from the server.

---

# HTTP 2

The primary goal of the research and development of a new version of HTTP centers around three qualities — Simplicity, High Performance, and Robustness. These goals are achieved by introducing capabilities that reduce latency in processing browser requests with techniques such as multiplexing, compression, request prioritization, and server push.

<aside>
💡 **Server Push** is a performance technique aimed at reducing latency by loading resources preemptively, even before the client knows they will be needed.

</aside>

The HTTP protocol allows servers to respond efficiently with more than the original content requested,  eliminating user intervention to continuously request information.

---

# SSL

**Secure Socket Layer (SSL)** provides security to the data that is transferred between a web browser and a server. It encrypts the link between a web server and a browser which ensures that all data passed between them remain private and free from attack.

### SSL Protocol Stack

![Untitled](Internet%20894cc7682445442e95c99adb26fb24f8/Untitled%201.png)

## Secure Socket Layer Protocols

### SSL Record Protocol

In the SSL Record Protocol application data is divided into fragments. The fragment is compressed and then encrypted MAC (Message Authentication Code) generated by algorithms like SHA (Secure Hash Algorithm) and MD5 (Message Digest Version 5) is appended.

### Handshake Protocol

The Handshake Protocol is used to establish a session between two devices. This protocol allows the client and server to authenticate each other by sending a series of messages to each other. The handshake is done in the following phases:

1. The client initiates the handshake by sending a “hello” message to the server. The message will include which SSL version the client supports, the cipher suites supported, and a string of random bytes.
2. In reply to the client's “hello” message, the server sends a message containing the server’s SSL certificate, the server’s chosen cipher suite, and another set of random strings.
3. The client verifies the server’s SSL certificate. This confirms that the server is who it says it is, and that the client is interacting with the actual owner of the domain.
4. The client sends one more random string of bytes which is encrypted with the public key and can only be decrypted with the private key by the server.

### Change-cipher Protocol

This protocol uses the SSL record protocol. Unless Handshake Protocol is completed, the SSL record output will be in a pending state. After the handshake protocol, the Pending state is converted into the current state.

Change-cipher protocol consists of a single message which is 1 byte in length and can have only one value.

### Alert Protocol

This protocol is used to convey SSL-related alerts to the peer entity. The alert levels are classified into two parts:

**Warning (level=1)**

This alert has no impact on the connection between sender and receiver. Some of them are:

1. Bad certificate: When the received certificate is corrupt.
2. No certificate: When an appropriate certificate is not available.
3. Certificate expired: When a certificate has expired.
4. Close notify: It notifies that the sender will no longer send any messages in the connection.

**Fatal Error (level=2)**

This alert breaks the connection between sender and receiver. Some of them are:

1. Handshake failure: When the sender is unable to negotiate an acceptable set of security parameters given the options available.
2. Decompression failure: When the decompression function receives improper input.
3. Illegal parameters: When a field is out of range or inconsistent with other fields.
4. Bad record MAC: When an incorrect MAC was received.
5. Unexpected message: When an inappropriate message is received.

---

# Web Browsers

A **Web Browser** is a software application used to access information on the **World Wide Web**. When a user requests some information, the web browser fatches the data from a web server and then displays the webpage on the user’s screen.

The main function of a browser is to present the web resource by requesting it from the server and displaying it in the browser window. The resource is usually an HTML document, PDF, image, or some other type of content.

<aside>
💡 The location of the resource is specified by the user using a URI (Uniform Resource Identifier).

</aside>

---

## Rendering Engine

The responsbility of a rendering engine is to render the HTML, CSS and JavaScript and display them to the user.

Different browsers use different rendering engines: Internet Explorer uses Trident, Firefox uses Gecko, Safari uses WebKit, and Opera uses Blink.

### Workflow

---

# URI (Uniform Resource Identifier)

A **URI** stands for **Uniform Resource Identifier**, is a string of characters that refers to a resource on the internet. It can identify any resource on the internet using name, location, or both.

A URI has two subsets; **URL (Uniform Resource Locator)** and **URN (Uniform Resource Name)**.

## URL

A **URL** is used to find the location of the resource on the web. A URL uses a protocol for accessing the resource, which can be HTTP, HTTPS, FTP, etc.

![Untitled](Internet%20894cc7682445442e95c99adb26fb24f8/Untitled%202.png)

## URN