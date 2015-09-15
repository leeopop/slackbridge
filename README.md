Docker container for [slack-irc](https://github.com/ekmartin/slack-irc)
===

### Installation
```
git clone https://github.com/leeopop/slackbridge
```

### Configuration

Copy `config.json.sample` to `config.json` and edit to your liking.

### Building and running

Build the docker container and run it with:

```
cd slackbridge/docker
docker build -t slackbridge .
docker run --restart=always -d -t slackbridge
```

Enjoy :)
