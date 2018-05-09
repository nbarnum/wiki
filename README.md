Forked from [prologic/wiki](https://github.com/prologic/wiki) to reduce Docker image size.

# wiki
[![GoDoc](https://godoc.org/github.com/prologic/wiki?status.svg)](https://godoc.org/github.com/prologic/wiki)
[![Go Report Card](https://goreportcard.com/badge/github.com/prologic/wiki)](https://goreportcard.com/report/github.com/prologic/wiki)
[![](https://images.microbadger.com/badges/image/nbarnum/wiki.svg)](https://microbadger.com/images/nbarnum/wiki "Get your own image badge on microbadger.com")

wiki is a self-hosted well uh wiki engine or content management system that
lets you create and share content in Markdown format.

### Source

```#!bash
$ go install github.com/prologic/wiki/...
```

## Usage

Run wiki:

```#!bash
$ wiki
```

Visit: http://localhost:8000/

Start creating/editing content!

## Configuration

By default wiki pages are stored in `./data` in the local directory. This can
be changed by supplying the `-data /path/to/data` option.

## Docker

Docker image is available at [Docker Hub](https://hub.docker.com/r/nbarnum/wiki/).

### Run Docker

```#!bash
docker run -p 8000:8000 nbarnum/wiki
```

With persistent data storage:

```#!bash
docker run -p 8000:8000 -v /path/to/your/data:/data nbarnum/wiki
```

To change the "Wiki" branding at the top of the page you can pass an environment variable "WIKI_BRAND":

```
docker \
  run -p 8000:8000 \
  -v /path/to/your/data:/data \
  -e WIKI_BRAND=MyWiki \
  nbarnum/wiki
```

### Build Docker

```#!bash
docker build -t $USER/wiki .
```

Remove the intermediate build image (and all other dangling images)

```#!bash
docker system prune
```

Then run the new image

```#!bash
docker run -p 8000:8000 $USER/wiki
```

## License

MIT
