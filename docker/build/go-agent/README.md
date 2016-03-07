##Usage
Start the container with this:

```docker run -ti -e GO_SERVER=your.go.server.ip_or_host gocd/gocd-agent```

If you need to start a few GoCD agents together, you can of course use the shell to do that. Start a few agents in the background, like this:

```for each in 1 2 3; do docker run -d --link angry_feynman:go-server gocd/gocd-agent; done```

##Getting into the container
Sometimes, you need a shell inside the container (to create test repositories, etc). docker provides an easy way to do that:

```docker exec -i -t CONTAINER-ID /bin/bash```

To check the agent logs, you can do this:

```docker exec -i -t CONTAINER-ID tail -f /var/log/go-agent/go-agent.log``` 