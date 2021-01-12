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
Removes a container if given a SHA

#### --> docker prune
Removes all stopped containers

## Generating a New Rails App Without Ruby Installed

Create a container that is interactive i.e. keeps STDIN open (`-i`), has a terminal emulator (`-t`), is ephemeral (`--rm`), and mounts a volume (`-v`), based on the `ruby:2.6` image.

```ruby
docker run -i -t --rm -v ${PWD}:/usr/src/app/ ruby:2.6 bash
```

Mounting a volume (`-v`) basically means sharing a portion of my local filesystem with the container. Specifically, for this example, we mounted the current directory in the container's `/usr/src/app`. "-v ${PWD}:/usr/src/app says, “Mount our current directory inside the container at /usr/src/app” (${PWD} is a Unix environment variable pointing to the current directory)".

Tell Docker to forward the bash session's CLI input on ot the Docker daemon (`-i`).

GOT_UP_TO_PAGE: 43 (DONE)
