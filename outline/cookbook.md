This section is still in the brainstorming phase. Most of the existing contents
and categories still need to be refined.

[Discussion](https://github.com/tokio-rs/doc-blitz/issues/23)

# Categories:

* [Application structure](#structure)
* [Concurrency](#concurrency)
* [File system](#fs)
* [Futures, Streams, Sinks](#futures-streams-sinks)
* [Networking](#networking)
* [Operating System](#os)
* [Time](#time)

<a name="structure"></a>
## Application structure

#### Background tasks

This shows how to spawn a task to perform work in the background. For example,
updating configuration on an interval.

How is the task shutdown when the application is shutdown.

#### Shutting down an application

How to signal to an application to shutdown.

* Listen for `ctrl-c`
* Gracefully shutdown open sockets
* Background tasks shutdown
* Setting a timeout

#### Managing state between tasks with message passing

An actor like pattern is used a lot with Tokio applications.

When there is a resource or state that needs to be accessed from many tasks, one
way to handle this is to spawn a task dedicated to managing that resource. Then,
all other tasks interact with the state via message passing.

This section probably can use multiple cookbook examples.

* Mutating a hashmap
* Managing a transport (see [here](https://github.com/tokio-rs/tokio/issues/86#issuecomment-358108788))

#### Performing CPU intensive operations

This cannot be done from the event loop and must be run on a thread pool
somehow.

<a name="concurrency"></a>
## Concurrency

TODO

<a name="fs"></a>
## File system

#### Send the contents of a file via a `TcpStream`.

How should this be done?

<a name="futures-streams-sinks"></a>
## Futures, Streams, Sinks

#### Returning different future types from different branches.

* Box
* `Either`

#### Process events from multiple sources

See
[here](https://github.com/tokio-rs/doc-blitz/issues/23#issuecomment-426481892)
and [here](https://github.com/tokio-rs/tokio/issues/86#issuecomment-358186680).

> What's the pattern for taking "events" from multiple sources and handling them
> all in the same handler? For example, waiting for network data, waiting for
> keyboard input, and a timer?

<a name="networking"></a>
## Networking

#### Connect a `TcpStream` by hostname (DNS).

How should this be done?

<a name="os"></a>
## Operating System

Most of the items from [Rust's
cookbook](https://rust-lang-nursery.github.io/rust-cookbook/intro.html#operating-system)
applies here.

#### Reading from STDIN

TODO

#### Writing to STDOUT

While `println` could work, this can block. What is the safe way to do this from
Tokio?

#### Child processes

How to spawn & manage child processes from Tokio?

<a name="time"></a>
## Time

#### Send a UDP packet every 5 seconds

Combo interval and networking. See [here](https://github.com/tokio-rs/doc-blitz/issues/23#issuecomment-426477390)

#### Limit a Stream by total duration

Terminate a stream when 30 seconds has elapsed. Then show how the number of
messages can be capped as well by using `take`
