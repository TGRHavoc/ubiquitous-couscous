---
title: "Installing"
weight: 1
---

Download the ZIP file. And extract the contents into `resources/live_map/`.

Add the following to your server.cfg file.

```
set socket_port 30121
set livemap_debug "info" # "[all]" 'trace', 'debug', 'info', 'warn', 'error', 'fatal', 'off'
set blip_file "server/blips.json"
set livemap_access_control "*"

start live_map
```

To get the in-game blips to show on the interface, you will need to generate a "blips" file.
This can be easily done with the in-game command `blips generate` (must be ran as admin).
