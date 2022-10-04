# Web Sockets

Traditionally, the web a been run on half duplex connections. That is, a client requests information, and a stream is opened to send that information. This works well for requesting documents to view. But for more interactive applications, the client and server need to respond to each other in real-time. To an extent, REST can do this. The client sends information in a GET or PUT request, for example, and the server responds. Then the client can process that response, and send another request. There is latency in this process. Web Sockets are an upgrade to HTTP that allows the client and server to communicate back and forth without the overhead of opening and closing an HTTP request for each volley of communication.

If a client wants to initiate a Web Socket, they can do so by first connecting via HTTP with an `Upgrade: websockets` header. Then, if the server supports it, the connections will be turned into a long lived Web Socket until it is closed by client or server. All this is taken care of by the browser on the client, and with Web Socket libraries on the server. [[reference to Wikipedia page]](https://en.wikipedia.org/wiki/WebSocket)

## Socket.io

Socket.io is a library for both client and server that instantiates a Pub/Sub messaging pattern over Web Sockets. Web Sockets makes it possible for the server to push a message to the client without the client polling the server. The Pub/Sub messaging pattern makes it easier for the server software to manage multiple clients.

### Socket.io API

The Socket.io API is similar to Node's EventEmitter API. They both have an `on()` method and an `emit()` method. They work similarly in both cases. `on()` sets up a `handler` function to listen for an event. `emit()` sends and event message to anything that is listening on it for that event. Where they differ is that while EventEmitter is designed to work on the server, Socket.io has a client library which will listen for the event over a Web Socket. [[reference to Socket.io tutorial on tutorialspoint.com]](https://www.tutorialspoint.com/socket.io/)
