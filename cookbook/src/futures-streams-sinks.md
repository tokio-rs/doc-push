# Futures, Streams, Sinks

## Returning different future types from different branches.

* Box
* `Either`

## Process events from multiple sources

See
[here](https://github.com/tokio-rs/doc-push/issues/23#issuecomment-426481892)
and [here](https://github.com/tokio-rs/tokio/issues/86#issuecomment-358186680).

> What's the pattern for taking "events" from multiple sources and handling them
> all in the same handler? For example, waiting for network data, waiting for
> keyboard input, and a timer?

