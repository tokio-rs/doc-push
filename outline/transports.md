Transports (`Stream + Sink` of frame values) in detail.

The [existing guide](https://tokio.rs/docs/going-deeper/frames/) is very
minimal.

# Pages:

* [Overview](#overview)
* [Implementing a transport](#implementing)
* [`Framed` and codecs](#framed)
* [Mapping values](#mapping)
* [Implementing protocols](#protocols)
* [Example: HTTP](#http)

<a name="overview"></a>
## Overview

**Status**: Unassigned.

An introduction to transports. What is a transport? Why are they important? When
should they be used?

#### Contents

* What is a transport?
* Why are they important?
* When should they be used?
* How are they used?
  * Most of this is covered in [futures, streams, and sinks][f-s-s], but a
    refresher in context of transports comes here.

[f-s-s]: futures-streams-sinks.md

<a name="implementing"></a>
## Implementing a transport

**Status**: Unassigned.

This section describes how to implement a transport by hand. While this is not
commonly done, the secion a) shows how the `Framed` and codec abstractions work
b) provide more examples of how to work with tokio.

#### Contents

* Quick review `Stream` and `Sink`.
* Implement line based transport by hand
  * Hard code `TcpStream`.
  * Abstract to `AsyncRead + AsyncWrite`.
* Implement basic length delimited transport.

<a name="framed"></a>
## `Framed` and codecs

**Status**: Unassigned.

Shows how to use the `Framed` and codec abstractions build the transports
introduced on the previous page.

#### Contents

* Implementing transport has some common patterns.
  * `Framed` handles most of the boilerplate.
* Introduce `Encoder`
* Introducd `Decoder`
* Implement lines codec
* Implement lengted delimite codec
* Show that these codecs exist in tokio
  * Show how to use them out of the box.

<a name="mapping"></a>
## Mapping values

**Status**: Unassigned.

Going from raw frames (`String` and `Bytes`) to richer values, for example JSON,
or `http` types.

#### Contents

* Transports are just `Stream + Sink` types
  * Transport combinators can map values
  * Transportation mapping layer can be implemented by hand too.
* Example: Use `serde` to encode / decode frame values
* TODO: What else goes here?

<a name="protocols"></a>
## Implementing protocols

**Status**: Unassigned.

Explains how additional protocol specific logic can be layered on as stream
combinators.

#### Contents

* Transports are just streams.
  * Combinators can be used to add more logic.
* Example: Ping / pong
  * Receive a ping frame, transparently respond with pong.
  * Implement `PingPong` transport decorator
* Show how using transport now does not require knowlege of ping / pong.

<a name="http"></a>
## Example: HTTP

**Status**: Unassigned.

Implement "minihttp" library.

#### Contents

* Define `HttpFrame` type as an enum of `Head` and `Body`.
* Implement `HttpCodec`.
* Show how to use transport
* Transparently handle `expect-100` request header.
