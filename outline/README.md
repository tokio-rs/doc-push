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

[Details](getting-started.md)

<a name="io"></a>
# I/O with Tokio

A deep dive into working with input/output with Tokio. After reading "getting started" and this section, the reader should be able to implement a network based application by implementing `Future` by hand.

[Details](io-with-tokio.md)

<a name="futures-streams-sinks"></a>
# Futures, Streams, and Sinks

In depth guides describing:

* What are futures, streams, and sinks?
* When should each be used?
* How are they used?
* How are they implemented?

[Details](futures-streams-sinks.md)

<a name="transports"></a>
# Transports

A transport is a `Stream + Sink` of frame values. This section gets into:

* What are transports?
* When should they be used?
* How do I build a transport?
* Transport middleware

and lots of examples.

[Details](transports.md)

<a name="time"></a>
# Tracking Time

Teaches how to incorporate time into Tokio applications. This covers `Delay` as
well as setting timeouts and `Interval` streams. The `clock` is also mentioned,
including how to mock it out.

[Details](tracking-time.md)

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

[Details](cookbook.md)

<a name="internals"></a>
# Internals

A guide covering how Tokio is built. This is not a tour of the code. Instead, it
covers enough concepts to have an idea of what Tokio is doing.

[Details](internals.md)
