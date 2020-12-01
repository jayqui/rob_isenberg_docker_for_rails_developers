# Chapter 1: A Brave New World

* An image is like a factory for a container.
* A container is an isolated environment for the execution of software.

## Play with initial commands

#### docker run
Creates a container based on the ruby:2.6 image and runs it
```ruby
docker run ruby:2.6 ruby -e "puts 'hello'"
```
Docker stores downloaded images locally, even caching individual layers of the image.

#### docker ps
List running containers
```ruby
docker ps
```

List running containers, including stopped ones
```ruby
docker ps -a
```
#### docker rm
Removes containers

## Generating a New Rails App Without Ruby Installed

Create an ephemeral (`--rm`) container from the `ruby:2.6` image with a terminal emulator (`-t`), and, (as the `root` user) run a bash session. Mount a volume (`-v`), basically sharing a portion of my local filesystem with the container—specifically, mounting the current directory in the container's `/usr/src/app`. Tell Docker to forward the bash session's CLI input on ot the Docker daemon (`-i`).
```ruby
docker run -i -t --rm -v ${PWD}:/usr/src/app/ ruby:2.6 bash
```

