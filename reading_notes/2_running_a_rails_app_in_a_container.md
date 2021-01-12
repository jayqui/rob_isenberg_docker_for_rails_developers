# Chapter 2: Running a Rails App in a Container

A Dockerfile is a set of instructions describing exactly how an image should be constructed.

Rationale: running a Dockerfile is an easily repeatable, fast way of getting a precisely configured container, the same way every time.

## My first dockerfile commands

#### FROM
specifies starting image -- want close to what you need but more general

(Trivia: `FROM scratch` is the minimal base image)

#### RUN
execute a command

#### COPY
`COPY . /usr/src/app` says "copy what's in my current directory into the container at `/usr/src/app`."

#### WORKDIR
specify the working directory for the container


## Building an image using a dockerfile

`docker build [options] path/to/build/directory`





### Today I learned
* To find which Linux version I'm on, the following three commands may be available:
  * `lsb_release -a`
  * `uname --all`
  * `cat /etc/os-release`

GOT_UP_TO_PAGE: 52
