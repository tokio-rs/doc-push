A guide covering how Tokio is built. This is not a tour of the code. Instead, it
covers enough concepts to have an idea of what Tokio is doing.

# Pages:

* [Overview](#overview)
* [Runtime model](#runtime-model)
* [Non-blocking I/O](#non-blocking-io)
* [Thread pool](#thread-pool)
* [Runtimes](#runtimes)

<a name="overview"></a>
## Overview

**Status**: Unassigned.

A high level overview of the Tokio crates. How do all the crates fit together?

#### Contents

TODO

<a name="runtime-model"></a>
## Runtime model

**Status**: [Complete](https://tokio.rs/docs/internals/runtime-model/)

An in depth guide of the Tokio runtiem model

<a name="non-blocking-io"></a>
## Non-blocking I/O

**Status**: [Complete](https://tokio.rs/docs/internals/net/)

How futures and Mio come together.

<a href="thread-pool"></a>
## Thread pool

**Status**: Unassigned.

A deep dive into the Tokio threadpool, algorithm, and scheduling heuristics.

#### Contents

TODO

<a href="runtimes"></a>
## Runtimes

**Status**: Unassigned.

How the runtime is put together. This also discusses `Park`.

#### Contents

This can be based on the [existing](https://tokio.rs/docs/going-deeper/building-runtime/) runtime guide, but should probably be tweaked to be focused on being an "internals" guide.
