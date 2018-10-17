# Application structure

## Background tasks

This shows how to spawn a task to perform work in the background. For example,
updating configuration on an interval.

How is the task shutdown when the application is shutdown.

## Shutting down an application

How to signal to an application to shutdown.

* Listen for `ctrl-c`
* Gracefully shutdown open sockets
* Background tasks shutdown
* Setting a timeout

## Managing state between tasks with message passing

An actor like pattern is used a lot with Tokio applications.

When there is a resource or state that needs to be accessed from many tasks, one
way to handle this is to spawn a task dedicated to managing that resource. Then,
all other tasks interact with the state via message passing.

This section probably can use multiple cookbook examples.

* Mutating a hashmap
* Managing a transport (see [here](https://github.com/tokio-rs/tokio/issues/86#issuecomment-358108788))

## Performing CPU intensive operations

This cannot be done from the event loop and must be run on a thread pool
somehow.


