# Drone (agent) on Dokku

Companion blog post [here]. Counterpart server repo [is here].

Steps:

* `dokku apps:create drone-agent`
* `dokku storage:mount /var/run/docker.sock:/var/run/docker.sock`
* `dokku docker-options:add build "--build-arg DRONE_SECRET=<SECRET HERE>"`
* `dokku docker-options:add deploy "--network drone_network"`
* `dokku docker-options:add run "--network drone_network"`
* `git push dokku`

[here]: https://blog.nootch.net/post/self-hosted-developer-bliss/
[is here]: https://github.com/sardaukar/dokku-drone-server
