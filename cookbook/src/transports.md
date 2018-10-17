# Transports

## Transparently send message when error is received on `Stream`

This is a form of automatic error handling at the transport level. Implement a
transport decorator that intercepts errors on the `Stream` half of a certain kind
