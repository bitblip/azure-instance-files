# Image
My custom windows container to host Astronner. https://github.com/bitblip/AstroneerServer It's actually really challenging to do this on windows.

Shockingly, Azure have even worse support for windows containers. File share mounts in the yaml file are not supported for windows containers. The image itself "mounts" the shares as a UNC shares inside windows and symbolically links the save and config directory.

# Control Panel
Image includes a neat web based control panel to admin the server. Load your container IP over HTTP and set the password the first time you start it.

# YAML Compose
Non 80 TCP ports are still a problem, the server will not be discoverable by the server browser but it does host.

```
az container create --resource-group <group> --file ./azure-compose.yaml
```