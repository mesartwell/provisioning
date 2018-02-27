# Docker containers for HTPC

Includes:

* Transmission+OpenVPN
* Plex
* Sonarr
* Radarr
* Jackett (tracker proxy)
* Watchtower (for auto-updating all the containers)
* Muximux (dashboard for all these apps)

## Usage

First, setup a .env file in this directory (set chmod 700) which contains the
settings mentioned in the docker-compose file.

Then 'up' the containers and it's off to the races!

```docker-compose up -d```

## Gotchas

* Configs for plex, sonarr, radarr can't be on a mergerfs fs with direct_io
  enabled.
* Plex cannot be setup as a server from LAN so I had to bootstrap by using
network_mode: "host", finishing server setup, and then flipping back to bridge
mode.

## Monitoring

* Need to configure docker to export metrics and prometheus to import them.
  [How-to](https://docs.docker.com/compose/compose-file/#labels-2).
