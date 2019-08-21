# Go 101 - Introduction to Go
[< Course overview](./)
<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-refresh-toc -->
**Table of Contents**

- [Go 101 - Introduction to Go](#go-101---introduction-to-go)
    - [Introduction](#introduction)
    - [About Go](#about-go)
        - [Why Go?](#why-go)
        - [Go where?](#go-where)
            - [Usecase: DutchSec](#usecase-dutchsec)
    - [Get Going](#get-going)
        - [Install go](#install-go)
            - [MacOS](#macos)
            - [Linux](#linux)
        - [go](#go)
        - [Set GOROOT](#set-goroot)
        - [Set GOPATH](#set-gopath)
        - [Set GOBIN](#set-gobin)
        - [Set up dirs](#set-up-dirs)
        - [Set up PATH](#set-up-path)
        - [Preparing SpaceMacs](#preparing-spacemacs)
            - [Enabling goimports](#enabling-goimports)
        - [Test run](#test-run)
    - [Test yourself](#test-yourself)
        - [Exercise 0: GOPATH](#exercise-0-gopath)
        - [Exercise 1: Binaries](#exercise-1-binaries)
        - [Exercise 2: Go env](#exercise-2-go-env)
        - [Exercise 3: Print something else](#exercise-3-print-something-else)

<!-- markdown-toc end -->

## Introduction
This course introduces the programming language Go. This first module mainly focuses on introducing Go and the `go` tool. This module also includes an installation guide.

This module ends with a series of exercises: you will play with the `go` tool and write your first line of Go.

This guide tries to be as complete as possible whilst also being as short as possible. That means that every line and example is there for a reason.

This guide also aims to be accessible to anyone who completed all of the courses listed in the course's requirements.

Have fun!

## About Go
Go, often refered to as *golang*, is a relatively young programming language that was created at Google. Go was announced in 2009 and saw it's first official release in 2012.

This course will use both *Go* and *Golang* to refer to the *Go programming language*.

### Why Go?
According to the creators of Go:
> Go was born out of frustration with existing languages and environments for systems programming. Programming had become too difficult and the choice of languages was partly to blame. One had to choose either efficient compilation, efficient execution, or ease of programming; all three were not available in the same mainstream language. - [golang.org/doc/faq/](https://golang.org/doc/faq#creating_a_new_language)

Google's Sameer Ajmani explains the need for Golang in this [video](https://youtu.be/5bYO60-qYOI?t=3m6s).

### Go where?
In the landscape of programming languages, Go stands somwhere between compiled languages such as C and C++ and interpreted languages like Java and Python.
![Go1](go01.png)  
*Go in the programming language landscape ([source](https://youtu.be/5bYO60-qYOI?t=3m6s))*

Go is used by well known companies such as Facebook, Twitter, Youtube, Apple and Dropbox. Widely used programs written in Go include Docker, Kubernetes, Soundcloud and InfluxDB. API's or clients for Go development are available for services and tools such as YouTube, Docker, Pulsar or Ethereum.

#### Usecase: DutchSec
Most of the software created at DutchSec is written in Go, for example [Honeytrap](https://github.com/honeytrap/honeytrap). This is because:
- Go's networking possibilities: networking is a great deal of DutchSec's core business.
- Go's system libraries: comprehensive io and os packages. 
- `gofmt` and type safety make it easy to work on projects with a large team of developers.
- Go is stable.
- Go compiles fast: one of the conditions the makers demanded.
- the whole program including dependencies are compiled into one file. No need for VM's or runtimes.
- Cross-compilation. It's fairly easy to compile a Go program for other architectures and operating systems. The most used architectures and operating systems are supported.
- Syntax is clean and simple. No need for unnescesary bracket or parenthesis.
- Integrated support for C libraries.
- Go also has object oriented-like features but uses them in a slighty different way. Go has no classes nor inheritence but uses alternative mechanisms to define relationships. Read [this blogpost](http://spf13.com/post/is-go-object-oriented/) to get a better understanding.
- Go really excels at _concurrency_. In Go, starting multiple processes at the same time is easy and without clutter.

![Go2](go02.png)
*Concurrency across programming languages. ([source](https://youtu.be/5bYO60-qYOI?t=3m6s))*

## Get Going
Getting started with Go is really simple. The setup process has three main steps: installing Go, setting a few environment variables and adding go to `PATH`.

### Install go
Assuming that you do not currently have Go installed on your machine, start by [installing Go](https://golang.org/doc/install) as described below for your operating system.

#### MacOS
MacOS users can download Go from the link provided above, however, Homebrew users can install Go by simply running `brew install go`.

#### Linux
Linux users that aren't happy with the installation instructions provided through the official website can have a look at [this guide](https://www.callicoder.com/golang-installation-setup-gopath-workspace/#linux).

### go
Test the new Go install by simply running `go`. Assuming the install is working correctly, Go will print it's help message (same as running `go help`).

Have a look at the help message `go` just printed for you. This should give you an idea of what you can [do](https://golang.org/cmd/go/) with `go`.

If your installation is working correctly, answer this question: how can you print your Go's version information using `go`?

### Set GOROOT
`GOROOT` is simply an environment variable that holds where the Go package is installed on your system.

To see the current value for `GOROOT` run:
```bash
go env GOROOT
```

Assuming a regular install, Go was installed in `/usr/local/go`. To set `GOROOT` to the afformentioned location, simply add the following line to your `~/.bashrc` (or similar file):
```bash
export GOROOT=/usr/local/go
```

A Homebrew install will probably come with a predefined `GOROOT`. If this is not the case on your system, you are looking for a location similar to `/usr/local/Cellar/go/1.12.9/libexec`.

If your Homebrew installed comes with a working `go env GOROOT` you should still set `GOROOT` in your `~/.bashrc` or similar. If `go env GOROOT` contains a value, it's easiet to set `GOROOT` to this value right away. In `~/.bashrc` or similar, simply add:

```bashrc
export GOROOT=$(go env GOROOT)

```

### Set GOPATH
[The `GOPATH` environment variable](https://github.com/golang/go/wiki/SettingGOPATH) specifies the location of your [Go workspace](https://www.callicoder.com/golang-installation-setup-gopath-workspace/#gopath-go-workspace-and-go-code-organization). It might be useful to change this if you want to, for example, use `~/dev/go/` as your Go workspace. If you do not set a `GOPATH` environment variable, Go will default to `~/go`.

When setting `GOPATH` to a directory that doesn't exist yet, remember to create it.

To see the current value for `GOROOT` run:
```bash
go env GOROOT
```

To permanently set `GOROOT`, again, add it to `~/.bashrc` (or similar).
```bash
export GOROOT=/usr/local/opt/go/libexec
```

### Set GOBIN
`GOBIN` can be used to specify where Go should store compiled programs (on succesfully running `go install`).

By defauly, `GOBIN` is set to nothing and Go stores compiled files in `$GOPATH/bin`. If you want Go to put it's new binaries somewhere else, you can specify another directory by setting GOBIN.

### Set up dirs
This step isn't super required, but smart. Ensure that the following directories exist (create them if they don't):
- Your `GOPATH` directory as set in `GOPATH`, or `~/go`.
- `$GOPATH/bin`, 
- `$GOPATH/pkg`, 
- `$GOPATH/src`

### Set up PATH
Finally, add Go to path adding this line to `~/.bashrc` or similar:
```bash
export PATH=$PATH:$GOROOT/bin
```

Finally, to make freshly compiled programs instantly available to you, add `$GOPATH/bin` to path by adding this line to `~/.bashrc` or similar:
```bash
export PATH=$PATH:$GOPATH/bin
```

### Preparing SpaceMacs
SpaceMacs users can follow these [instructions](https://github.com/syl20bnr/spacemacs/tree/master/layers/%2Blang/go) to properly set up Go mode.

To be safe, make sure to set `GOROOT`, `GOPATH`, `GOBIN`.

When upgrading from an older version of Go, it might be a good idea to update your SpaceMacs packages (this can be done from the SpaceMacs home buffer (`SPC b h`)).

Note that the Go mode doc states to ensure that `syntax-checking` and `auto-completion` are turned on in `.spacemacs` (edit this file with `SPC f e d`). 

#### Enabling goimports
Open `.spacemacs` (`SPC f e d`) and look for:
```elisp
(defun dotspacemacs/user-config ()
```
Now add:
```elisp
(setq gofmt-command "goimports")
```

Your lines should look similar to:
```elisp
(defun dotspacemacs/user-config ()
  "Configuration function for user code.
This function is called at the very end of Spacemacs initialization after
layers configuration.
This is the place where most of your configurations should be done. Unless it is
explicitly specified that a variable should be set before a package is loaded,
you should place your code here."
  (setq gofmt-command "goimports")
  )
```

If you added a line to this section of your `.spacemacs` and are unsure how to add another one, take a look at this example containing two lines:
```elisp
(defun dotspacemacs/user-config ()
  "Configuration function for user code.
This function is called at the very end of Spacemacs initialization after
layers configuration.
This is the place where most of your configurations should be done. Unless it is
explicitly specified that a variable should be set before a package is loaded,
you should place your code here."
  (display-time-mode 1)
  (setq gofmt-command "goimports")
  )
```

### Test run
Verify everything is working as it should by following the instructions in the [tutorial from before](https://www.callicoder.com/golang-installation-setup-gopath-workspace/#testing-your-go-installation-with-the-hello-world-program).

## Test yourself

### Exercise 0: GOPATH
What does `GOPATH` do?

### Exercise 1: Binaries
Where does `go install` output binaries to?

### Exercise 2: Go env
Find out how to print all Go environment variables using the `go` tool.

### Exercise 3: Print something else
Using the test program from the [Test run](#test-run) chapter, create a new program called `learning`. This program should print `I'm learning!` instead of `Hello, World.` Create a binary in `$GOBIN`.
