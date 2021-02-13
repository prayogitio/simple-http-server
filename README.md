## Simple TCP Implementation

The objective of this repository is to learn how to implement TCP using Socket programming.  
We create a server and a client.  
The client will send request message to the server and the server will send response message to the client.

### Server
We create a socket and bind it to an address with specified port.  
The server will keep listening and will wait for some request from the client.  
Whenever new request arrived, which is a new socket from client, the server will get the request message.  
The server can do whatever it wants againts the message. For example, the server can parse the message to check if it is a HTTP request or not according to RFC rules for HTTP. Or maybe the server can parse the request to check which file the client is requesting.  
There are many other actions that can be performed by the server.

### Client
We create a socket and bind it to an address with specified port.  
The client will send a message through that socket.  
The message can be anything. For example, plain text, HTTP request, image, json, and so on.  
The server, which is hosting on a specified host and port, will retrieve the message and process it. Then, the server will send a message as a response to the client.  
The client will show the response message to the user.

## Operate the code

### Run the Server
Open a terminal and execute this command:
```
gcc -o server-side tcp-server-side-code.c && ./server-side
```

### Run the Client
On a separate terminal, execute this command:
```
gcc -o client-side tcp-client-side-code.c && ./client-side
```

On the server terminal, you should see something like this:
```
+++++ Waiting for new connection +++++

Hello from client
--------- Hello message sent --------------

+++++ Waiting for new connection +++++
```

On the client terminal, you should see something like this:
```
Hello message sent
HTTP/1.1 200 OK
Content-Type: text/plain
Content-Length: 12

Hello World!
```

You can also open your favourite browser and access `http://localhost:8082`. You should see `Hello World!`

That's it! Thank you for learning with me.