Running tasks concurrently

# Pages:

* [Overview](#overview)
* [Channels](#channels)
* [Backpressure](#backpressure)

<a name="overview"></a>
## Overview

**Status**: Unassigned.

Overview of concurrency and parallelism with Tokio.

#### Contents

* Concurrency in an asynchronous system.
  * Asynchronous gets you the ability to run concurrent tasks.
  * Concurrency is not parallelism.
    * Parallelism requires running on multiple cores.
  * Parallelism is required to scale on modern servers
    * Modern servers have many cores.
* Runtimes.
  * Runtimes execute many tasks concurrently (link previous runtime section).
    * Two variants, one parallel and one not.
    * `spawn` adds a new task, the task is executed concurrently.
  * `tokio::run`
    * Concurrent and parrallel (if the system supports it).
    * Runs multiple OS threads.
    * Tokio tasks are multiplexed across multiple threads.
      * M:N scheduling.
  * `tokio::runtime::current_thread`
    * Concurrent, but **not** parrallel.
    * Single OS thread.
  * Pros / cons to both
  * Uses Rust to enforce thread-safety.
    * Tasks spawned on `tokio::run` must be `Send`.
    * Tasks spawned on `runtime::current_thread` do not require `Send`.

<a name="channels"></a>
## Channels

**Status**: Unassigned.

Message passing for managing concurrency. This covers both oneshot and mpsc.

#### Contents

* Concurrency requires coordination
  * Thread-safe as well (when parrallel).
  * Many coordination/synchronization primitives that work in "synchronous"
    modes of programming do not carry over to asynchronous.
    * Mutexes don't work -- not possible to implement a future aware Mutex.
* Message passing
  * Primary method of coordination
  * How it might be used in real apps.
  * Example of message passing.
  * Two kinds of channels, `oneshot` and `mpsc`.
* `oneshot`
  * Send a single value
  * One sender, one receiver
  * Bunch of examples
* `mpsc`
  * Send many values from potentially many sources.
  * One receiver

* Message passing for managing concurrency
  * Discuss the strategy of using messages to manage concurrency.
* oneshot
  * Send a single value across tasks
  * Examples
* mpsc
  * Examples
  * https://github.com/rust-lang-nursery/futures-rs/pull/984#issuecomment-383792953

<a name="backpressure"></a>
## Backpressure

**Status**: Unassigned.

Backpressure needs to be discussed in the guides. Should it be here?
[Discussion](https://github.com/tokio-rs/doc-push/issues/53)

#### Contents

TODO
