Dredd
===========
An unofficial docker image with [Dredd][link-dredd].

[![docker layers][img-docker-layers]][link-microbadger]
[![docker pulls][img-docker-pulls]][link-registry]

## Usage

```bash
$ docker run \
    --rm \
    --tty \
    --link 'container_name' \
    --network 'network_name' \
    --volume '/path/to/api-description.apib:/blueprint.apib' \
    --volume '/path/to/hook.js:/hook.js' \
    bugyik/dredd /blueprint.apib container_name --hookfiles /hook.js
```

[link-dredd]: https://github.com/apiaryio/dredd
[link-microbadger]: https://microbadger.com/images/bugyik/dredd
[link-registry]: https://hub.docker.com/r/bugyik/dredd

[img-docker-layers]: https://images.microbadger.com/badges/image/bugyik/dredd.svg
[img-docker-pulls]: https://img.shields.io/docker/pulls/bugyik/dredd.svg?style=flat-square
