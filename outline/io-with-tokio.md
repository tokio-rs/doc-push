Covers working with I/O in depth with Tokio.

# Pages:

* [Overview](#overview)
* [Reading and writing data](#reading-writing)
* [`poll_` API](#poll_api)
* [Implementing `AsyncRead` / `AsyncWrite`](#impl-async-read-write)
* [Filesystem](#fs)
* [Datagram APIs](#datagram)

<a name="overview"></a>
## Overview

**Status**: Unassigned.

Functions as an introduction / tutorial to using I/O with Tokio.

#### Contents

* Comes w/ TCP, UDP, Unix
* Non-blocking
  * Backed by Mio
  * based on runtime model (previous section).
* Setup a TCP server
* Connect with TcpStream
* Send some data using `io::write_all`
* Read data on server, print, and close socket (note on drop).

<a name="reading-writing"></a>
## Reading and writing data

**Status**: Unassigned.

An in depth guide to reading and writing data using Tokio's TCP types.
This section may also briefly talk about other I/O types such as `File`
from `tokio-fs`. On this page, combinators and future based APIs are
used exclusively.

#### Contents

* Quick intro to `AsyncRead` / `AsyncWrite` traits
  * Refresher: non-blocking
* Reading data w/ combinators
  * `io::read_exact`
    * Should an `io::read` combinator be added?
      * Perhaps the `BytesCodec` should be introduced here? That
        adds `Stream + Sink` which hasn't been discussed yet.
  * `io::lines`
* Writing data w/ combinators
* `split()`
  * Why is split needed? When should split be used?
  * `io::copy`
  * Spawn read / write on other tasks

<a name="poll_api"></a>
## `poll_` API

**Status**: Unassigned.

Using the `poll_` based APIs for reading and writing data. This page
talks about the lower level API and explains how the combinators
described on the previous page work. There should be plenty of examples.

#### Contents

* Dig more into `AsyncReady` trait.
  * `poll_read` function.
    * Tie in with runtime model.
  * Disclaimer: `AsyncRead` extends `std::io::Read`... mistake
  * When to use `poll_read` vs. combinators? (quick answer then link
    to combinator vs/ manual future impl discussion).
  * Example: implement `ReadExact`.

* Dig into `AsyncWrite` trait.
  * `poll_write` function
  * `poll_flush` function.
  * `shutdown` function
    * In `std`, blocking cleanup ops are done in drop handler.
    * `shutdown` performs this work, like flushing.
    * Socket is safely dropped after `shutdown` returns `Ok(Ready)`.
    * Sometimes it isn't possible:
      * Alternative: spawn task w/ socket to do cleanup work.

#### Open questions

* What should this page be titled?

<a name="impl-async-read-write"></a>
## Implementing `AsyncRead` / `AsyncWrite`

**Status**: Unassigned.

The previous page focused on using `AsyncRead` and `AsyncWrite`. This
page explains how to implement these two traits. It explains when you
would implement `AsyncRead` or `AsyncWrite` for a type and how to do it.

#### Contents

* Decorating an `AsyncRead` implementation.
  * Example 1) Adding metrics.
    * Track total number of bytes returned by `poll_read`.
  * Example 2) Implementing `Peek<T: AsyncRead>`.
    * `Peek` implements `AsyncRead`
    * `Peek` provides `poll_peek` function that returns the next
      bytes w/o consuming.
* Decorating an `AsyncWrite` implementation
  * Implement basic buffering (`BufWriter<T: AsyncWrite>`).
    * Be sure to call out `shutdown` implementation.
* Implementing `AsyncRead`/`AsyncWrite` for a `T: mio::Evented`.
  * `PollEvented` utility.

<a name="buf-apis"></a>
## `_buf` APIs

**Status**: Unassigned.

A brief introduction and tutorial to the `bytes` crate. This page shows
how the `_buf` APIs provide an easier way to read / write data. This
page also explains vectored I/O and why it is important. It then ties in
`But` and `BufMut` to vectored I/O, explaining how `Buf` and `BufMut`
traits may be backed by multiple byte slices and `AsyncRead` /
`AsyncWrite` implementations may read and write these byte slices in
batches.

#### Contents

* `read_buf` / `write_buf`.
* Brief `bytes` introduction.
* vectored I/O

#### Open questions

* What should this page be titled?

<a name="fs"></a>
## Filesystem

**Status**: Unassigned.

A guide of Tokio's file system APIs.

#### Contents

TODO

<a name="datagram"></a>
## Datagram APIs

**Status**: Unassigned.

A guide of Tokio's datagram API. This guide will focus mostly on UDP,
but can mention other datagram APIs towards the end (Unix datagram?)

#### Contents

TODO: contents
