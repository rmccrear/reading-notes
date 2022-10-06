# Socket.io: Rooms and Namespaces

## A simple chat example.

If we look at a simple chat example ([reference](https://socket.io/get-started/chat/)) taken from the Socket.io getting started page, we can get a feel for what Socket.io is good for.

In this example, we have clients who want send chat-messages to each other. The sever is the go-between, passing the messages back and forth.

In the simplest case, a client will send a message to the server intended for any other client who happens to be connected at the time. Then the server will receive the message from the client. It will then relay the message to all clients listening at the time.

If a client connects to the server, it will trigger a "connected" event on the server. When the connection is lost, a "disconnected" event will be triggered. This way the server can keep track of all the users that are connected and which socket they are on.

# Rooms

Rooms are a way of organizing who receives messages that are emitted from the server. Each client's socket is automatically joined into a default room, which contains just the client. There are not others in this default "room". A room can be created on the server side, and client sockets and be joined to the room. Then a message is emitted in that room, all the client sockets will receive the message.

Two rooms can be joined together in a union. This means that all the sockets in each of the rooms will get the messages that are emitted in that new, larger room. (If someone is in both rooms, they will get not get the message twice.) Since each socket is represented as being in a room with just themselves, joining two sockets together form a room, makes a room with two, and so on.

Clients' sockets can be maid to leave a room, by calling `leave`.

# Namespaces

Namespaces are another way of orginzing how messages are past. Namespaces have their own events, rooms, and middleware. It's like having a new instance of your `io` object separated from the other. It's analogous to a different path on an HTTP server.

If you have systems that are not closely related, you can give them their own namespace. For example, in the chat app, you might have a wiget that shows who is online. In this example, you need the data from the server about who is online, but you will have a different stream of communicaion from the chat section of the app.
