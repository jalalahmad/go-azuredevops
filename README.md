# go-azuredevops

[![GoDoc](https://godoc.org/github.com/jalalahmad/go-azuredevops/azuredevops?status.svg)](https://godoc.org/github.com/jalalahmad/go-azuredevops/azuredevops)
[![Build Status](https://travis-ci.org/jalalahmad/go-azuredevops.png?branch=master)](https://travis-ci.org/jalalahmad/go-azuredevops)
[![codecov](https://codecov.io/gh/jalalahmad/go-azuredevops/branch/master/graph/badge.svg)](https://codecov.io/gh/jalalahmad/go-azuredevops)
[![Go Report Card](https://goreportcard.com/badge/github.com/jalalahmad/go-azuredevops?style=flat-square)](https://goreportcard.com/report/github.com/jalalahmad/go-azuredevops)

`go-azuredevops` is a Go client library for accessing the [Azure DevOps API](https://docs.microsoft.com/en-gb/rest/api/vsts/). This is very much work in progress, so at the moment supports a small subset of the API.

## Services

There is partial implementation for the following services

* Boards
* Builds
* Favourites
* Iterations
* Pull Requests
* Work Items

## Usage

```go
import "github.com/jalalahmad/go-azuredevops/azuredevops
```

Construct a new Azure DevOps Client

```go
v := azuredevops.NewClient(account, project, token)
```

Get a list of iterations

```go
iterations, error := v.Iterations.List(team)
if error != nil {
    fmt.Println(error)
}

for index := 0; index < len(iterations); index++ {
    fmt.Println(iterations[index].Name)
}
```
