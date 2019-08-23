# 103 - Advanced Go

[< Course overview](./)  
[< Previous course module](./102_intermediate_go.md)

<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-refresh-toc -->
**Table of Contents**

- [103 - Advanced Go](#103---advanced-go)
    - [Introduction](#introduction)
    - [Outside of Go](#outside-of-go)
    - [Learning go](#learning-go)
        - [While learning Go](#while-learning-go)
        - [These are some useful introductions to Go:](#these-are-some-useful-introductions-to-go)
        - [Excercises](#excercises)
        - [Testing](#testing)
        - [Reference](#reference)
    - [Required reading/watching/listening](#required-readingwatchinglistening)
        - [Data](#data)
        - [Packages](#packages)
        - [Goroutines and channels](#goroutines-and-channels)
        - [Interfaces](#interfaces)
        - [Protocols](#protocols)
            - [HTTP](#http)
            - [Websocket](#websocket)
        - [Dep](#dep)
        - [Go and Docker](#go-and-docker)
        - [Interesting Go talks](#interesting-go-talks)
        - [Additional resources](#additional-resources)

<!-- markdown-toc end -->

## Introduction
This course introduces the programming language Go.

This module mostly contains links to educational materials you should dive into.

Have fun!

## Outside of Go
- Understand [pipes](https://ryanstutorials.net/linuxtutorial/piping.php) STDIN / STDOUT / STDERR

## Learning go
### While learning Go
- Get to know all the basic packages. Al lot of work has already been done and you don't have to reinvent the wheel.
- Use multiple sources/tutorials while learning Go.
- You can try Golang in a browser. From the official [website](https://play.golang.org/) and with colored syntax plus documentation [here](https://goplay.space/).
- Channels and Go-routines are powerful tools. Use them to your advantage.

### These are some useful introductions to Go:
- Miek Gieben has made a nice book  about [Learning Go](https://miek.nl/downloads/2015/go.pdf)(pdf warning).  
- Caleb Doxsey wrote this introduction for Go both on the [web](https://www.golang-book.com/books/intro) as a [PDF](https://www.golang-book.com/public/pdf/gobook.0.pdf)
- Alan Donovan and Brian Kernighan wrote [The Go Programming Language](http://www.gopl.io/). 
- A Tour of [Go](https://tour.golang.org/) by Google.  
- Safaribook Online - Introduction to [Go](https://www.safaribooksonline.com/library/view/introducing-go/9781491941997/preface01.html#idp72384)  

### Excercises
Test your skills and see if you can crack these [excersises](https://exercism.io/tracks/go/exercises).

Have a look at the various answers by other users.

### Testing
- Go has a testing [package](https://golang.org/pkg/testing/) package.
- Video on [testing](https://www.youtube.com/watch?v=ndmB0bj7eyw) in Go.

### Reference
- The complete [Go Programming Language Specification](https://golang.org/ref/spec)  
- Tutorial on [for loops](http://golangtutorials.blogspot.com/2011/06/control-structures-go-for-loop-break.html)

## Required reading/watching/listening
### Data
- A string is not a [string](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- Blogpost about [strings](https://blog.golang.org/strings) in Go.
- Strings to bytes and [why](https://medium.com/go-walkthrough/go-walkthrough-bytes-strings-packages-499be9f4b5bd)
- Great explanation on how Go appends to slices for you and what happens [internally](https://blog.golang.org/go-slices-usage-and-internals)
- Getting a grasp on [pointers](https://dave.cheney.net/2017/04/26/understand-go-pointers-in-less-than-800-words-or-your-money-back)
- [Pointer example .go file](https://github.com/Opensource-Academy/go/tree/master/examples/pointers)

### Packages
You don't have to re-invent the wheel. Go has core packages that so you don't have to build everything from scratch. Learning how to use them will make your life a lot easier:
- Strings package: [strings](https://golang.org/pkg/strings/) 
- Input & output: [io package](https://golang.org/pkg/io/) 
- Files & folders [os package](https://golang.org/pkg/os/) 
- Errors [error package](https://golang.org/pkg/errors/)
- Hashes & cryptography [crypto package](https://golang.org/pkg/crypto/)
- Servers: [net package](https://golang.org/pkg/net/). This is where the power of Golang comes in. Networking is made very easy and the net package has built in protocols as http, tcp and rcp.
  
### Goroutines and channels
Concurrency in Go is powerful when implemented correctly.
- This is a great [video](https://youtu.be/f6kdp27TYZs) where Rob Pike explains Go channels, goroutines and patterns with example code.  
- Divan has made concurrency [visual](http://divan.github.io/posts/go_concurrency_visualize/) for you and explains this in a [video](https://www.youtube.com/watch?v=KyuFeiG3Y60).  
- Tutorial about concurrency and [wait-groups](https://medium.com/@matryer/very-basic-concurrency-for-beginners-in-go-663e63c6ba07)

### Interfaces
You can use interfaces in a few different ways to really boost your code. 
- Read this [post](http://spf13.com/post/is-go-object-oriented/) by Steve Francia about structs, methods and interfaces and how it relates to OOP.

### Protocols
Learn about all the different protocols you'll probably going to work with.
#### HTTP
- Great explanation of the HTTP protocol and how it communicates can be found [here](https://www.tutorialspoint.com/http/index.htm) and [here](https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177)

#### Websocket
WebSockets provide a persistent connection between a client and server that both parties can use to start sending data at any time.

- A websocket begins as a HTTP request but then upgrades to a websocket connection.

### Dep

Dep is a dependency management tool for the Go language. With `go get` you can install packages (imports) in your GOPATH folder so that they are available for every project.
However, when you are working on lots of different project, you don't always want to install all the packages. That's where Dep comes in.
Dep allows you to install and maintain the packages (and which versions) you need just for that project.
- Check the dep [website](https://golang.github.io/dep/) for how to use dep.

### Go and Docker
- Nice [blogpost](https://blog.docker.com/2016/09/docker-golang/) how to use Go and Docker.
- Build [standalone](https://hub.docker.com/_/golang/) Docker images that run Go.
- Complete [repository](https://github.com/docker-library/golang) with different Go versions and base images.

### Interesting Go talks
- [Google I/O 2012 - Go Concurrency Patterns](https://www.youtube.com/watch?v=f6kdp27TYZs)
  A basic (and quick) introduction (with examples) for concurrent programming in Go. Very usefull for getting a quick overview of concurrent go programming.
- [Google I/O 2013 - Advanced Go Concurrency Patterns](https://www.youtube.com/watch?v=QDDwwePbDtw)
  As the title describes, this talks goes more in depth about concurrent programming in Go. This too is a video that show a very quich but detailed overview.
- [Effectivity of Go](https://www.youtube.com/watch?v=cQ7STILAS0M) explained by one of the creators

### Additional resources
- Information for all the packages in Go from the official [website](https://golang.org/pkg/)
- Dave Cheney has a nice [page](https://dave.cheney.net/resources-for-new-go-programmers) with valuable resources for Go.
- A curated [list](https://awesome-go.com/) of awesome Go frameworks, libraries and software.
- A series of [walkthroughs ](https://medium.com/go-walkthrough)to help you understand the Go standard library better.
