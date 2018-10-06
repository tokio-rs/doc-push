The getting started guides start with a Tutorial then go into a high
level tour of necessary knowledge for being productive with Tokio.

# Pages:

* [Hello world!](#hello-world)
* [Futures](#futures)
* [Error Handling](#errors)
* [Example: A Chat Server](#chat-server)

<a name="hello-world"></a>
## Hello world!

**Status**: [Complete](https://tokio.rs/docs/getting-started/hello-world/)

A "Hello world!" Tokio tutorial. Implement a server that writes "hello world" to
the socket.

<a name="futures"></a>
## Futures

**Status**: unassigned.

A high level overview of how and when execution happens in Tokio, how futures
are lazy and the basics of the polling model.

### Contents

* High level Explanation of Tokio's runtime model and how it is significantly different than other languages.
* Explanation that Tokio's futures are lazy. If the future is not spawned, no work will ever be done.
* High level explanation of Tokio's polling model.

<a name="errors"></a>
## Error Handling

**Status**: unassigned

The very basics of error handling

### Contents
* High level explanation of future's error handling model
* High level explanation of how to recover when something goes wrong.

<a name="chat-server"></a>
## Example: Chat Server

**Status**: [Complete](https://tokio.rs/docs/getting-started/chat/)

A tutorial showing how to implement a chat server.