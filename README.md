# Errors

A wrapper over [pkg/errors](https://github.com/pkg/errors) to enrich and enhance error handling.

# Usage

To use this package, you need to have [pkg/errors](https://github.com/pkg/errors) and this package in your system. For most cases this should mean doing

```shell
go get github.com/pkg/errors
go get github.com/vabshere/errors
```

Then import this package as `import "github.com/vabshere/errors"`.

Create a new error:

```go
err := NewError("Error happened")
```

Almost all of the functions support formatted strings so you can also do something like:
 
```go
num := 5
err := NewError("Errors occured %d times", num)
``` 
 
To chain a new error with an existing one,  use functions starting with the name *Chain*-. For example:

```go
err := NewError("Error happened")
err = ChainError(err, "This happened due to another error")
```

This will link the original error as the causer for the new error.

# Reference

All functions starting with *New*- in their name returns a fresh new error and those with *Chain*- in their name returns an `error` chained with the input `error`.

Check out the [docs](https://godoc.org/github.com/vabshere/errors) to know more.
