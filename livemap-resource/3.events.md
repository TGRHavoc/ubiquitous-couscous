---
title: "Events"
weight: 3
---

In an effort to make the addon useful to other developers, I've created a few events that can be used to make changes to the data being sent to the UI.

## Client to server

Below you can find some info on the server events that __must__ be triggered by the client.

Note, when using `livemap:AddPlayerData` or `livemap:UpdatePlayerData` if the player has been removed using `livemap:RemovePlayer` they will be tracked again.

| Name                     |        Parameters        | Description                                                                                  |
| ------------------------ | :----------------------: | -------------------------------------------------------------------------------------------- |
| livemap:AddPlayerData    | key (string), data (any) | Adds data to a player that gets sent over Websockets                                         |
| livemap:UpdatePlayerData | key (string), data (any) | Updates the data that is associated with the player. Uses the same "key" as the above event. |
| livemap:RemovePlayerData |       key (string)       | Removed data associated with the player. Uses the same "key" as the above events.            |
| livemap:RemovePlayer     |                          | Stops sending a player data over Websockets                                                  |
| livemap:AddBlip          |   table (blip to add)    | Adds a blip to the "blip_file" so that it can be showed on the web interface                 |
| livemap:UpdateBlip       |  table (blip to update)  | Updates the blip to the table  given                                                         |


Example usage:
```lua
-- Set the player's "Name" to "Havoc"
TriggerServerEvent("livemap:AddPlayerData", "Name", "Havoc")

-- Update the player's name to "John Doe"
TriggerServerEvent("livemap:UpdatePlayerData", "Name", "John Doe")

-- Remove "Name" from the player (stops displaying it in the UI)
TriggerServerEvent("livemap:RemovePlayerData", "Name")

-- Removes a player from the websockets (stops tracking them)
TriggerServerEvent("livemap:RemovePlayer")

-- Adds a blip to the interface
TriggerServerEvent("livemap:AddBlip", {
    "sprite" = 16, -- Jet. You can find IDs at https://github.com/TGRHavoc/live_map-interface/blob/master/js/src/markers.1.js#L64
    "pos" = {
        x = 0.0,
        y = 0.0,
        z = 100.0
    },
    "name" = "This is a blip",
    "description" = "This is to show how one can add blips to the interface"
})

-- Updates the blip at the position. 
TriggerServerEvent("livemap:UpdateBlip", {
    "sprite" = 51, -- Drugs
    "pos" = {
        x = 0.0,
        y = 0.0,
        z = 100.0
    },
    "name" = "I'm now a drug store",
    "description" = ""
})

```

### Blip structure
The structure of the blip is as follows:
```lua
{
    sprite = Number (required) -- The sprite used when creating the blip
    pos = Table (requires) -- contains the X Y and Z coordinates of the blip
    {
        x = Float (required) -- X coordinate of the blip
        y = Float (required) -- Y coordinate of the blip
        z = Float (required) -- Z coordinate of the blip
    }
    name = String (optional) -- Name to show on the interface (defaults to the name of the blip e.g. "Drugs")
    description = String (optional) -- Description of the blip shown on the interface
}
```

## Server Events

Below you can find information on some server-only events. This can only be called on the server.

| Name                              |                   Parameters                   | Description                                                                                        |
| --------------------------------- | :--------------------------------------------: | -------------------------------------------------------------------------------------------------- |
| livemap:internal_AddPlayerData    | identifier (string), key (string), value (any) | Adds data with the key that gets sent over Websockets for the player with the specified identifier |
| livemap:internal_UpdatePlayerData | identifier (string), key (string), value (any) | Updated the data that is associated with the player with the identifier                            |
| livemap:internal_RemovePlayerData |       identifier (string), key (string)        | Removed the data that is associated with the player with the identifier                            |
| livemap:internal_RemovePlayer     |              identifier (string)               | Removes a player from the websocket data array (stops tracking the player)                         |

Example usage:
```lua
-- Get the player's identifier
identifier = GetPlayerIdentifier(source, 0)

-- Set the player's "Name" to "Havoc"
TriggerEvent("livemap:internal_AddPlayerData", identifier, "Name", "Havoc")

-- Update the player's "Name"  to "John Doe"
TriggerEvent("livemap:internal_UpdatePlayerData", identifier, "Name", "John Doe")

-- Removes the player's "Name"
TriggerEvent("livemap:internal_RemovePlayerData", identifier, "Name")

-- Removes the player
TriggerEvent("livemap:internal_RemovePlayer", identifier)

```
