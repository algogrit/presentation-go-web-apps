layout: true

.signature[@algogrit]

---

class: center, middle

# Go Web Apps

Gaurav Agarwal

---
class: center, middle

## `net/http` package

---

- Supports both `http` & `https`

- Also has support for certificate management

- Simple and powerful

---

- `http.ListenAndServe(<address>, <router>)`

- `r.Handle(<route>, <router>)`

- `r.HandleFunc(<route>, <handlerFunc>)`

---
class: center, middle

### Introducing [`gorilla` toolkit](https://www.gorillatoolkit.org/)

---
class: center, middle

#### `mux` [package](https://github.com/gorilla/mux)

---

#### [Other packages](https://www.gorillatoolkit.org/) of interest

- `gorilla/handlers`
- `gorilla/csrf`
- `gorilla/sessions`

- `gorilla/websocket`
- `gorilla/rpc`

---
class: center, middle

### [Project Layout](https://github.com/golang-standards/project-layout)

---
class: center, middle

### Clean Code Architecture

---
class: center, middle

![Clean Architecture](assets/images/CleanArchitecture.jpg)

---

#### Layers

- Entities (entities)

  Defines all the Models in the application

- Repository

  Encapsulates the interaction with the database. This is the lowest layer in the application.

- Services

  Orchestrates the interaction with repository and other services.

---

#### Layers (continued)

- Transport

  Encapsulates the interaction with application over an http API

- Binaries

  The code in `cmd/server` ties all the layers together, in order the start the app.

---
class: center, middle

Sample App: [YAES Server](https://github.com/algogrit/yaes-server)

---
class: center, middle

### Advance Testing

---
class: center, middle

#### Mocking

---
class: center, middle

*Go is a statically typed language.*

---
class: center, middle

[gomock](https://github.com/golang/mock) is a mocking framework for the Go programming language.

---
class: center, middle

#### HTTP Testing

---
class: center, middle

[`net/http/httptest`](https://golang.org/pkg/net/http/httptest/)

---
class: center, middle

#### Concurrency Testing

---
class: center, middle

## gRPC

---

- Works on top of HTTP 2

- Usually, uses protobuf for messaging, JSON is optional

  - Uses *proto3* syntax

- Auto-generates client and server side stubs

---

- Supports both a unary (request-response) rpc as well as streaming (two-way communication)

- Middleware are known as interceptors

- Isn't well supported in the browser

---
class: center, middle

### Install protobuf for your platform

---

#### For Mac

```bash
brew install protobuf
```

---

### Install go gRPC plugin

```bash
go get github.com/golang/protobuf/protoc-gen-go
```

---

### Steps

- Define a new `.proto` file
- Generate stubs using:
  `protoc --go_out=plugins=grpc:. --go_opt=paths=source_relative api/<filename>.proto`
- Implement the server

---
class: center, middle

Code
https://github.com/algogrit/presentation-go-web-apps

Slides
https://go-web-apps.slides.algogrit.com
