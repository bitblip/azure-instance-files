# Image
Using feature rich image https://github.com/lloesche/valheim-server-docker

# Docker Compose
Docker compose is a dead-end until Azure supports configuring multiple ports and non 80 TCP.

# YAML Compose
Non 80 TCP ports are still a problem, the server will not be discoverable by the server browser but it does host.

## Variables
The following variables must be configured.

* `<label>` DNS and Server name
* `<world>` The Valheim world name
* `<password>` Password needed to join the game
* `<account>` Azure Storage account name
* `<key>` Azure Storage access key
* `<data-share>` Share name from Azure Storage File Share to save game state
* `<config-share>` Share name from Azure Storage File Share to save game configs

```
az container create --resource-group <group> --file ./azure-compose.yaml
```

# Storage
Container uses two shares to maintain server sate.

`vhserver-data` and `vhserver-config`