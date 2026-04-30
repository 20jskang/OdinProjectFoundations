# How Does the Web Work?

---

## How does the Internet work?

The **Internet** is the backbone of the Web, the technical infrastructure that makes the Web possible. At its most basic, the Internet is a large network of computers which communicate all together.

The history of the Internet is somewhat obscure. It began in the 1960s as a US-army-funded research project (Development of the first Internet, ARPANET), then evolved into a public infrastructure in the 1980s with the support of many public universities and private companies. The various technologies that support the Internet have evolved over time, but the way it works hasn't changed that much: Internet is a way to connect computers all together and ensure that, whatever happens, they find a way to stay connected.

<div align="center">
**Aaron Titus's Internet explained in 5 minutes.**

 [![How the Internet Works in 5 Minutes by Aaron Titus](assets/AaronTitusHowDoesTheInternetWork.avif)](https://www.youtube.com/watch?v=7_LPdttKXPc)

</div>

---

### A simple network

When two computers need to communicate, you have to link them, either physically (usually with an Ethernet cable) or wirelessly (for example with Wi-Fi or Bluetooth systems). All modern computers can sustain any of those connections.


<p align="center">
  <img src="assets/twoComputersLinkedTogether.png" alt="Two computers linked">
</p>


Such a network is not limited to two computers. You can connect as many computers as you wish. But it gets complicated quickly. If you're trying to connect, say, ten computers, you need 45 ables, with nine plugs per computer!


 <p align="center">
  <img src="assets/tenComputersLinkedTogether.png" alt="Ten computers linked">
</p>


To solve this problem, each computer on a network is connected to a special tiny computer called a **network switch** (or switch for short). The single purpose of the switch is to make sure that messages sent from a given computer arrive only at their target destination computer. To send a message to computer B, computer A sends the message to the switch, which in turn forwards the message to computer B, computer B doesn't get messages intended for other computers, and none of the messages for computer B reach other computers on the local area network.

Once we add a switch to the system, our network of computers only require 10 cables: a single plug for each computer and a switch with 10 plugs (This is much more manageable).

---

## Browsing the Web
### The difference between web pages, website, web server, and search engine

We will start by describing various web-related concepts: web pages, websites, web servers, and search engines. 

**Web page**
    A document that can be displayed in a web browser. These are also often called just "pages". Such documents are written in the HTML language.

**Website** 
    A collection of web pages grouped together into a single resource, with links connecting them together. Often called a "site".

**Web server**
    A computer that hosts a website on the Internet. Think of it as a big computer that is directly connected to the Internet.

**Web service**
    A software responds to requests over the Internet to perform a function or provide data. A web service is typically backed by a web server, ad may provide web pages for users to interact with. Many websites are also web services, though some websites (such as MDN) consist of static content only. Examples of web services would be something that resizes images, provides a weather report or handles user login.

**Search engine**
    A web service that helps you find other web pages, such as Google, Bing, Yahoo, or DuckDuckGo. Search engines are normally accessed through a web browser (for example, you can perform search engine directly in the address bar of Firefox, Chrome, etc.) or through a web page (for example, bing.com or duckduckgo.com).

--- 

## How the Web works

Computers connected to the internet are called **clients** and **servers**.

- Clients are the typical web user's internet-connected devices (for example, your computer connected to your Wi-Fi, or your phone connected to your mobile network) and web-accessing software available on those devices.
- Servers are computers that store webpages, sites, or apps.  When a client wants to access a webpage, a copy of the webpage code is downloaded from the servers to the client machine, where it is rendered by the browser and displayed to the user. 

### The other parts of the toolbox
For data to get back and forth between the client and the server, you need the following things:

**Your internet connection:**
Allows you to send and receive data on the internet. It's basically like the street between your house and the shop.

**TCP/IP (Transmission control protocol and Internet Protocol):**
TCP/IP are communication protocols that define how data should travel across the internet. This is like the transport mechanisms that let you place an order, go to the shop, and buy your goods.

**DNS**
The **Domain Name System (DNS)** is like an address book for websites. When you type a web address in your browser, the browser looks at the DNS to find the website's IP address, the actual address the server is located at, before it can retrieve the website. The browser needs to find out which server the website lives on, so it can send HTTP messages to the right place. This like looking up the address of the shop before you visit it.

**HTTP**
**Hypertext Transfer Protocol(HTTP)** is an application protocol that defines a language for clients and server to speak to each other. 

**Files**
A website is made up of many different files. These files come in two main types:
    - Code: Websites are built primarily from HTML, CSS, and JavaScript - the different programming languages websites are written in, which the browser interprets and assembles into a web page to display to user
    - Assets: This is collective term for all the other items that appear on a website - such as images, music, video, Word documents, and PDFs - that aren't code that the browser interprets.

### So what happens, exactly?
When you type a web address (which is technically part of a URL) into your browser address bar, the following steps occur:
    1. The browser goes to the DNS server and finds the real address of the server that the website lives on.
    2. The browser sends an HTTP request message to the server, asking it to send a copy of the website to the client. This message, and all other data sent between the client and the server, is sent across your internet connection using TCP/IP.
    3. If the server approves the client's request, the server sends the client a "200 OK" messages and then starts sending the website's files to the browser as a series of small chunks called packets.
    4. The browser assembles the small chunks into a complete web page and displays it to the user.

### DNS 
Real web addresses (URLs) aren't the nice, memorable strings you type into your address bar to find your favorite websites. They are special numbers that look like this: 192.0.2.172

This is called an IP address, and it represents a unique location on the web. However, it's not very easy remember, is it? That's why the Domain Name System was invented. This system uses special servers that match up a web address you type into your browser (like google.com) to the website's real (IP) address. Large websites are commonly made available on multiple servers, so they load efficiently for different users worldwide. As a result, the IP address may vary depending on where you are. 

### How does a DNS request work?
As we already saw, when you want to display a webpage in your browser it's easier to type a domain name than an IP address. Let's take a look at the process:

    1. Type google.com in your browser's location bar.
    2. Your browser asks your computer if it already recognizes the IP address identified by this domain name (using a local DNS cache). If it does, the name is translated to the IP address and the browser negotiates contents with the web server. 
    3. If your computer does not know which IP is behind the google.com name, it goes on to ask a DNS server, whose job is precisely to tell your computer which IP address matches each registered domain name.
    4. Now that the computer knows the requested IP address, your browser can negotiate contents with the web server.

---

<div align="center">
**DNS Explained by DNS Made Easy Videoes**

 [![DNS Explained](https://i.ytimg.com/vi/72snZctFFtA/hq720.jpg?sqp=-oaymwFBCNAFEJQDSFryq4qpAzMIARUAAIhCGAHYAQHiAQoIGBACGAY4AUAB8AEB-AH-CYAC0AWKAgwIABABGD8gZShkMA8=&rs=AOn4CLCiaqCwaNdD6Z-XcpJt7tr6_sOoJw)](https://www.youtube.com/watch?v=72snZctFFtA&t=45s)

</div>

---

### Packets 
Earlier, we used the term "packets" to describe the format in which the data is transferred between the client and the server. 

When data is sent across the web, it is sent in multiple small chunks called packets. Each packet contains:

    1. A header, which includes a detail such as the server and client IP address, the packet number, the total number of packets in the transmission, and details of the protocols used in the transmission.
    2. A payload, which contains the actual data sent in the packet.

There are multiple reasons why data is sent in small packets, but most significantly:
    - They are sometimes dropped or corrupted, and when this happens, it's quicker and easier for the client to request the missing packets rather than an entire file.
    - The packets can be routed along different paths, making the transmission as efficient as possible and reducing the possibility of traffic causing slowdowns of the network - especially when many users are requesting the same resource simultaneously. The packets may arrive out of sequence, but the client can use the information in the packet headers to make sure they are assembled in the correct order.
