---
title: "Configuration"
weight: 2
---

# Configuration

There isn't much to configure with the resource.
It's built to be as plug-n-play friendly as possible.

The important stuff you may want to change can be done so with the convars below.

### Convars
The following convars are available for you to change

| Name                   | Type   |       Default Value | Description                                                                                                                                                                        |
| ---------------------- | ------ | ------------------: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| socket_port            | int    |               30121 | Sets the port the socket server should listen on                                                                                                                                   |
| livemap_debug          | string |              "warn" | Sets how much information gets printed to the console ("[all]" 'trace', 'debug', 'info', 'warn', 'error', 'fatal', 'off')                                                          |
| blip_file              | string | "server/blips.json" | Sets the file that will contain the generated blips that is exposed via HTTP                                                                                                       |
| livemap_access_control | string |                "\*" | Sets the domain that is allowed to access the blips.json file (E.g. "https://example.com" will only allow the UI on http://example.com to get the blips), "\*" will allow everyone |


    pipe_tables, raw_html, fenced_code_blocks, auto_identifiers, gfm_auto_identifiers, backtick_code_blocks, autolink_bare_uris, space_in_atx_header, intraword_underscores, strikeout, task_lists, emoji, shortcut_reference_links, angle_brackets_escapable, lists_without_preceding_blankline. 