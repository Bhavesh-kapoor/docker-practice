# Hello Captain — Basic Dockerfile

A simple Docker project that uses Alpine Linux and prints a greeting when the container starts.

## Dockerfile

The Dockerfile uses `alpine:latest` as the base image.

```dockerfile
FROM alpine:latest

ENV NAME=Captain

CMD ["sh", "-c", "echo Hello, $NAME!"]
```

## Build the Docker Image

Run this command from the project root:

```bash
docker build -t hello-captain .
```

## Run the Container

### Default name

```bash
docker run --rm hello-captain
```

Output:

```text
Hello, Captain!
```

### Pass your own name

You can pass a name using the `NAME` environment variable:

```bash
docker run --rm -e NAME=Bhavesh hello-captain
```

Output:

```text
Hello, Bhavesh!
```

## How It Works

* `FROM alpine:latest` — uses Alpine Linux as the base image.
* `ENV NAME=Captain` — sets `Captain` as the default name.
* `CMD` — runs when the container starts.
* `sh -c` — allows the shell to expand `$NAME`.
* `--rm` — automatically removes the container after it exits.
* `-e NAME=Bhavesh` — overrides the default `NAME` at runtime.

## Requirements

* Docker installed
* Docker daemon running

## Commands Summary

```bash
docker build -t hello-captain .
docker run --rm hello-captain
docker run --rm -e NAME=Bhavesh hello-captain
```
