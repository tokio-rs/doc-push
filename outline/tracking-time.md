Covers all time related topics.

There is an [existing](https://tokio.rs/docs/going-deeper/timers/) guide, but it
is minimal.

# Pages:

* [Overview](#overview)
* [Timeouts](#timeouts)
* [The clock and testing](#clock)

<a name="overview"></a>
## Overview

**Status**: Unassigned.

Functions as an introduction / tutorial to working with time

#### Contents

Items to cover:

* The passage of time is represented as a future that completes when the
  duration has elapsed.
* Cannot call `thread::sleep` as that blocks the thread.
* Show how to use `Delay`.
  * Just a future, combine with `and_then` to schedule work to happen after a
    duration.
  * There is no need to cancel a delay if it is no longer needed, just drop.
* Show how to use `Interval` ([existing](https://tokio.rs/docs/going-deeper/timers/#running-code-on-an-interval).
  * Some examples.
  * Use combinators like `take(n).and_then(...)` to repeat an action `n` times
    w/ a delay between.
* With [cancellation](https://github.com/tokio-rs/doc-blitz/issues/20), when the
  `Delay` future completes first, simply dropping the future for the "timed out"
  operation is sufficient.
* Include timer implementation notes [existing](https://tokio.rs/docs/going-deeper/timers/#notes-on-the-timer).
* Link to cookbook section on time.

<a name="timeouts"></a>
## Timeouts

**Status**: Unassigned.

Guide showing how to use the `timeout` combinator with futures and streams.

[Existing guide](https://tokio.rs/docs/going-deeper/timers/#timing-out-a-long-running-operation).

#### Contents

* Unlike sync apis, there are no `_timeout` variants. for example, with blocking
  sockets, read and write timeouts would be set and calls to `read` and `write`
  would block for at most that amount of time. with non-blocking sockets,
  speciality functions are not needed. instead, conceptually one "selects" the
  operation with a `delay` future.
* Show how to timeout a read w/ Tokio
  * `timeout` combinator is on `FutureExt` trait, included in prelude.
* Show how to timeout a stream (each value has a max alloted time to yield).
* Show how to timeout processing a stream.
  * This is setting a timeout on the `Stream::for_each` future.

<a name="clock"></a>
## The clock and testing

**Status**: Unassigned.

Reliable tests cannot rely on the passage of time. Tokio's `clock` can be
overridden, allowing a mock clock to be injected.

#### Contents

* Discussion of writing reliable tests with time.
* Show [`clock`](https://docs.rs/tokio/0.1.11/tokio/clock/index.html) API
  * How to use is replacing `Instant::now()` with `tokio::clock::now()`.
* Tokio's time APIs (`Delay`, `Timeout`, `Interval`, ...) use `clock`
  internally.
* Example: mocking out time in a test.
