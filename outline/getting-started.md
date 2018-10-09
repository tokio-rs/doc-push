The getting started guides start with a tutorial then goes into a very high
level tour of necessary knowledge for being productive with Tokio.

# Pages:

* [Hello world!](#hello-world)
* [Futures and Stream](#futures)
* [The Tokio Runtime](#rumtime)
* [Example: An Echo Server and Client](#echo)

<a name="hello-world"></a>
## Hello world!

**Status**: [Complete](https://tokio.rs/docs/getting-started/hello-world/)

A "Hello world!" Tokio tutorial. Implement a TCP client that writes "hello world" to
a TCP stream.

<a name="futures"></a>
## Futures and Streams

**Status**: rylev

A high level overview of futures including how futures are lazy, as well as an
overview of Streams (as the iterator version of futures).

### Contents

* Explanation that Tokio's futures are lazy. If the future is not spawned, no work
  will ever be done.
* High level explanation of Streams.

<a name="runtime"></a>
## Tokio Runtime

**Status**: rylev

A high level overview of how and when execution happens in Tokio, spawning
tasks on the runtime, and the basics of the polling model.

### Contents

* High level Explanation of Tokio's runtime model and how it is significantly
  different than other languages.
* Explanation of running tasks on the runtime.
* High level explanation of Tokio's polling model.

<a name="echo"></a>
## Example: Echo Server and Client

**Status**: rylev

A tutorial showing how to implement an echo server and client.