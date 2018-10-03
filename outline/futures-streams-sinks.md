In depth guide into Futre, Stream, and Sink types.

# Pages:

* [Overview](#overview)
* [Working with Futures](#working-with-futures)
* [Working with Streams](#working-with-streams)
* [Working with Sinks](#working-with-sinks)
* [Putting it Together](#putting-it-together)

<a name="overview"></a>
## Overview

**Status**: Unassigned.

Futures were introduced in the getting started section. This page is a
more in-depth guide into what a Future is conceptually, why it makes
sense to represent async computations using futures. Then, it expand
this into what Streams and Sinks are at a high level.

#### Contents

* What is the difference between a future, stream, and sink?
* Disclaimer: Tokio's futures are very different than what other
  languages provide.

<a name="working-with-futures"></a>
## Working with Futures

**Status**: Unassigned.

TODO: Description

#### Contents

* Intro
  * Summarize the overview page
* Combinators
  * What is a combinator?
  * What kind of combinators are there?
    * Survey of the various kinds of combinators and examples of how
      to use them.
  * Shortcomings of combinators (move by value, no borrowing).
  * Must write in a fully functional style.
  * Common patterns with futures
  * Reach often for custom combinators (implementing Future).
* Implementing custom combinators
  * TODO: Good rule of thumb for when to reach for this
  * TODO: What are some good examples to work thorugh?
* Tasks (vs. Futures)
  * Quick note, tasks are "just" a future representing the
    completion of the task's computation.
  * Common problem: Not mapping a future to `Item = (), Error = ()`

<a name="working-with-streams"></a>
## Working with Streams

**Status**: Unassigned.

TODO: Description

#### Content

* More detailed description fo streams, when to use them.
  * Examples of types that implement stream.
* Combinators.
  * What kind of combinators are there?
    * Survey of the various kinds of combinators and examples of how
      to use them.
* Implementing custom combinators
  * TODO: What should go here?

<a name="working-with-sinks"></a>
## Working with Sinks

**Status**: Unassigned.

TODO: Description

#### Contents

* More detailed description fo streams, when to use them.
  * Examples of types that implement stream.
    * `mpsc::Sender`.
    * `BytesCodec` (hint at transports).
* Combinators
  * Not as many combaintors, combinators make most sense on the
    "pull" side of things vs. push.
  * `fanout`, `buffer`
* How to use Sink?
  * `send`, `send_all`, `flush`
* Implementing `Sink`
  * Implement a basic channel (backed by a `VecDeque`)
  * How is `Fanout` implemented.

<a name="putting-it-together"></a>
## Putting it Together

**Status**: Unassigned.

TODO: Description

#### Contents

* How to structure an application using Tokio?
  * Looping

TODO: Fill this out

# Open questions

* Can the section title be better?
