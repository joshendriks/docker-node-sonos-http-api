# docker-raspberry-node-sonos-http-api
Docker wrapper for https://github.com/jishi/node-sonos-http-api

![](http://dockeri.co/image/joshendriks/docker-raspberry-pi-node-sonos-http-api)

![](http://dockeri.co/image/joshendriks/docker-raspberry-pi2-node-sonos-http-api)

![](http://dockeri.co/image/joshendriks/docker-raspberry-pi3-node-sonos-http-api)

## Usage
Refer to https://github.com/jishi/node-sonos-http-api for all the configuration detail

First make the config and local dirs up
```shell
mkdir clips
mkdir cache
mkdir presets
curl https://raw.githubusercontent.com/jishi/node-sonos-http-api/master/presets/example.json > presets/example.json
echo {} > settings/settings.json
```

Then run the docker image
```shell
docker run \
  --net=host \
  --name sonos \
  --restart=always \
  -d \
  -v `pwd`/settings.json:/app/settings.json \
  -v `pwd`/clips:/app/static/clips \
  -v `pwd`/cache:/app/cache \
  -v `pwd`/presets:/app/presets \
  joshendriks/docker-raspberry-pi-node-sonos-http-api 
```
