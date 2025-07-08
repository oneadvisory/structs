This is a copy of the repo https://github.com/fatih/structs which is no longer being maintained. It has been tweaked
a little to better support our use case.


# Archived project. No maintenance. 

This project is not maintained anymore and is archived. Feel free to fork and
make your own changes if needed. For more detail read my blog post: [Taking an indefinite sabbatical from my projects](https://arslan.io/2018/10/09/taking-an-indefinite-sabbatical-from-my-projects/)

Thanks to everyone for their valuable feedback and contributions.

# Structs [![GoDoc](http://img.shields.io/badge/go-documentation-blue.svg?style=flat-square)](http://godoc.org/github.com/fatih/structs) [![Build Status](http://img.shields.io/travis/fatih/structs.svg?style=flat-square)](https://travis-ci.org/fatih/structs) [![Coverage Status](http://img.shields.io/coveralls/fatih/structs.svg?style=flat-square)](https://coveralls.io/r/fatih/structs)

Structs contains various utilities to work with Go (Golang) structs. It was
initially used by me to convert a struct into a `map[string]interface{}`. With
time I've added other utilities for structs.  It's basically a high level
package based on primitives from the reflect package. Feel free to add new
functions or improve the existing code.

## Install

```bash
go get github.com/fatih/structs
```

## Usage and Examples

Just like the standard lib `strings`, `bytes` and co packages, `structs` has
many global functions to manipulate or organize your struct data. Lets define
and declare a struct:

```go
type Server struct {
	Name        string `json:"name,omitempty"`
	ID          int
	Enabled     bool
	users       []string // not exported
	http.Server          // embedded
}

server := &Server{
	Name:    "gopher",
	ID:      123456,
	Enabled: true,
}
```

