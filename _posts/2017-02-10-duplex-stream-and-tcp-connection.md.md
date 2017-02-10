---
layout:     post
title:      Duplex stream and TCP connection
date:       2017-02-10 12:00:00
summary:    This article describes duplex stream in nodejs in brief. I have demonstrated how duplex stream is used to establish connections between two processes using socket.
categories: programming nodejs stream net tcp sockets client-server
---

Stream is one of the coolest abstraction provided by the nodejs core.There are three types of stream:  
- Readable 
- Writable 
- Readable + Writable 

Duplex stream falls under the third category. You can both read from it as well as write to it. If you like to imagine, think of duplex stream as something like telephone. It allows two way simultaneous connection. See how **a** is used in below statement.

```js 
  a.pipe(b).pipe(a)
```    
Here **a** is a duplex stream acting both as readable and writable stream. 

TCP connection in nodejs is a represented by socket object which is a duplex stream. So Let's try creating TCP connection between two nodes A and B as 

```js
A <----> B
```

Let's assign A to be a server and B to be client and establish a TCP connection between them creating a **client-server** architecture.

Let's make A(server) to listen on port number 8000

```js
  //a.js
  var net = require('net')
  
  var server = http.createServer(function (socket) {

    //socket acting as readable stream
    socket.on('data', function (data) {
    console.log(data.toString())
    })

    //socket acting as writable stream
    socket.write("Hello I am A")

  })
  
  server.listen(8000)
```

Let's make B(client) establish TCP connection with A(server)

```js
  //b.js
  var net = require('net')

  var socket = net.connect(8000, 'localhost')
  
  //socket acting as readable stream
  socket.on('data', function (data) {
    console.log(data.toString())
  })

  //socket acting as writable stream
  socket.write("Hello I am B")
```

Here in both programs (A and B)  socket is the duplex stream that is acting as TCP to provide transport facility between A and B. 

Above communication architecture can be represented as :

![1]({{ site.url }}/images/duplex.png)

Now let us run the above programs(a.js and b.js)

Open up a terminal and run program a

```sh
  $ node a.js
```

Open another terminal and run program b.

```sh
  $ node b.js
```
If there are no errors in the program , it should printing something like this:

a.js outputs 
```
  Hello I am B
```

b.js outputs
```
  Hello I am A
```

Here A and B have tcp connection between each other and are receiving what the other end is sending to it and printing it.


### Learn more about streams

- [Stream Handbook](https://github.com/substack/stream-handbook)
- [Stream Adventure Workshop](https://github.com/workshopper/stream-adventure)
