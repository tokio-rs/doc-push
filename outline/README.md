The outline for what we would like the Tokio guides to become.

#### Sections

* [Getting started](#getting-started)
* [I/O with Tokio](#io)
* [Futures, Streams, and Sinks](#futures-streams-sinks)
* [Transports](#transports)
* [Tracking Time](#time)
* [Tokio for...](#tokio-for)
* [Cookbook](#cookbook)
* [Internals](#internals)

<a name="getting-started"></a>
# Getting started

The "getting started" section is a quick introduction to the aspects of Tokio required to be productive. This section is currently mostly written, but requires some improvements.

[Details](01-getting-started.md)

<a name="io"></a>
# I/O with Tokio

A deep dive into working with input/output with Tokio. After reading "getting started" and this section, the reader should be able to implement a network based application by implementing `Future` by hand.

[Details](02-io-with-tokio.md)

<a name="futures-streams-sinks"></a>
# Futures, Streams, and Sinks

In depth guides describing:

* What are futures, streams, and sinks?
* When should each be used?
* How are they used?
* How are they implemented?

[Details](03-futures-streams-sinks.md)

<a name="transports"></a>
# Transports

A transport is a `Stream + Sink` of frame values. This section gets into:

* What are transports?
* When should they be used?
* How do I build a transport?
* Transport middleware

and lots of examples.

[Details](04-transports.md)

<a name="time"></a>
# Tracking Time

Teaches how to incorporate time into Tokio applications. This covers `Delay` as well as setting timeouts and `Interval` streams. The `clock` is also mentioned, including how to mock it out.

[Details](05-tracking-time.md)

<a name="tokio-for"></a>
# Tokio for...

A set of guides showing how to use Tokio in different contexts:

* Servers
* Clients
* Game development
* Libraries

[Details](tokio-for.md)

<a name="cookbook"></a>
# Cookbook

[TODO](https://github.com/tokio-rs/doc-blitz/issues/23)

[Details](06-cookbook.md)

<a name="internals"></a>
# Internals

[TODO](https://github.com/tokio-rs/doc-blitz/issues/28)

[Details](07-internals.md)
