# Client

## Getters 

### int: client:getid

```lua
client:getid()
```

Returns the client's id.

### int: client:getstate

```lua
client:getstate()
```

Returns the client's state.

| Index | Name                  | Description                   |
|-------|-----------------------|-------------------------------|
|   0   | CLIENT_STATE_INITIAL  | Player just connected         |
|   1   | CLIENT_STATE_MOTD     | Player is receiving the map   |
|   2   | CLIENT_STATE_INGAME   | Player is in game             |

### string: client:getaddr

```lua
client:getaddr()
```

Returns the client's IP Address.

### int: client:getping

```lua
client:getping()
```

Returns the client's ping to the server.

### string: client:getname

```lua
client:getname()
```

Returns the client's name.

### string: client:getskin

```lua
client:getskin()
```

-

### int: client:getgroup

```lua
client:getgroup()
```

-

### int: client:getheldblock

```lua
client:getheldblock()
```

Returns the client's held block ID.

### string: client:getdispname

```lua
client:getdispname()
```

Returns the client's display name.

### string: client:getappname

```lua
client:getappname()
```

Returns the client's app name.

For example: ``ClassiCube 1.3.1``, ``Vanilla Client`` etc.

### bool: client:getposition

```lua
client:getposition(Vector: position)
```

Writes the client's position in the given vector.

### Vector: client:getpositiona

```lua
client:getpositiona()
```

Returns the client's position.

### bool: client:getrotation

```lua
client:getrotation(Angle: angle)
```

Writes the client's rotation in the given angle.

### Angle: client:getrotationa

```lua
client:getrotationa()
```

Returns the client's rotation.

### float: client:getclickdist

```lua
client:getclickdist()
```

Returns the client's click distance.

### int: client:getfluidlvl

```lua
client:getfluidlvl()
```

Returns the client's fluid level.

| Index | Description               |
|-------|---------------------------|
|  0    | Not in a liquid.          |
|  1    | Swimming in a liquid.     |
|  2    | Sinking in a liquid.      |

### int: client:getstandblock

```lua
client:getstandblock()
```

Returns the block ID the client is standing on.

### int: client:getmodel

```lua
client:getmodel()
```

Returns the client's model ID.

0 --> 255 are blocks; 256 is the player; 257 are custom models.

### World: client:getworld

```lua
client:getworld()
```

Returns the world the client is currently on.

### bool: client:islocal

```lua
client:islocal()
```

Returns whether or not the client is local.

### bool: client:isspawned

```lua
client:isspawned()
```

Returns whether or not the client is spawned.

### bool: client:isinsameworld

```lua
client:isinsameworld(Client: other)
```

Returns whether or not the client is in the same world as the ``other`` client.

### bool: client:isfirstspawn

```lua
client:isfirstspawn()
```
Returns whether or not this is the client's first spawn.

### bool: client:isinstate

```lua
client:isinstate(EClientState: state)
```
Returns whether or not the client is in a given EClientState.

| Name                  | Description                   |
|-----------------------|-------------------------------|
| CLIENT_STATE_INITIAL  | Player just connected         |
| CLIENT_STATE_MOTD     | Player is receiving the map   |
| CLIENT_STATE_INGAME   | Player is in game             |

### bool: client:isop

```lua
client:isop()
```
Returns whether or not the client is OP.

### bool: client:isbot

```lua
client:isbot()
```
Returns whether or not the client is a bot.

## Setters

### client:setop

```lua
client:setop(bool: op)
```

Sets the client's OP status.

### client:setspawn

```lua
client:setspawn(Vector: position, Angle: angle)
```

Sets the client's spawn position and rotation.

### client:setgroup

```lua
client:setgroup(int: groupID)
```

Sets the client's group.

Requires ``client:update()`` afterwards.

### client:setrotation

```lua
client:setrotation(short: X, short: Y, short: Z)
```

Sets the client's model's rotation.

Requires ``client:update()`` afterwards.

### client:setweather

```lua
client:setweather(EWeather: weather)
```

Sets the client's local weather

| Index | Name                  |
|-------|-----------------------|
|   0   | WORLD_WEATHER_SUN     |
|   1   | WORLD_WEATHER_RAIN    | 
|   2   | WORLD_WEATHER_SNOW    |

### client:setenvprop

```lua
client:setenvprop(EProp: property, int: value)
```

Sets a client's EnvProp. For more information, please look at [CPE SetMapEnvProp](https://wiki.vg/Classic_Protocol_Extension#SetMapEnvProperty_packet)


| Index | Name                          |
|-------|-------------------------------|
|   0   | WORLD_PROP_SIDEBLOCK          |
|   1   | WORLD_PROP_EDGEBLOCK          | 
|   2   | WORLD_PROP_EDGELEVEL          |
|   3   | WORLD_PROP_CLOUDSLEVEL        |
|   4   | WORLD_PROP_FOGDIST            |
|   5   | WORLD_PROP_SPDCLOUDS          |
|   6   | WORLD_PROP_SPDWEATHER         |
|   7   | WORLD_PROP_FADEWEATHER        |
|   8   | WORLD_PROP_EXPFOG             |
|   9   | WORLD_PROP_SIDEOFFSET         |

### client:setenvcolor

```lua
client:setenvcolor(EColor: env_color, Color3: color)
```

Sets a client's EnvColor. For more information, please look at [CPE EnvSetColor](https://wiki.vg/Classic_Protocol_Extension#EnvSetColor_Packet)

| Index | Name                  |
|-------|-----------------------|
|   0   | WORLD_COLOR_SKY       |
|   1   | WORLD_COLOR_CLOUD     |
|   2   | WORLD_COLOR_FOG       |
|   3   | WORLD_COLOR_AMBIENT   |
|   4   | WORLD_COLOR_DIFFUSE   |

### client:setclickdist

```lua
client:setclickdist(int: clickDistance)
```

Sets a client's click distance.

### client:setblockperm

```lua
client:setblockperm(int: blockID, bool: place, bool: break)
```

Sets a client's block permissions.

### client:setmotd

```lua
client:setmotd(string: serverName, string: serverMotd)
```

Sends the client a new name and motd.

### client:sethotkey

```lua
client:sethotkey(string: command, int: keycode, int: modifier)
```

Sets a hotkey to a given command. You can find a list of keycodes [here](https://gist.github.com/Mumfrey/5cfc3b7e14fef91b6fa56470dc05218a).

!!! note
    You can add ``\n`` at the end of the command to make it instantly execute.

!!! warning
    The modifier is a bitflag, therefore 3 is skipped in the list below.

| Index | Modifier |
|-------|----------|
| 0     | None     |
| 1     | Ctrl     |
| 2     | Shift    |
| 4     | Alt      |

### client:setmodel

```lua
client:setmodel(int: modelID)
```

```lua
client:setmodel(string: modelName)
```

Sets a client's model. Accepts either modelID or modelName.

Requires ``client:update()`` afterwards.

### client:setdispname

```lua
client:setdispname(string: displayName)
```

Sets the client's display name.

Requires ``client:update()`` afterwards.

### client:sethotbar

```lua
client:sethotbar(int: slot, int: blockID)
```

Sets ``slot`` from the client's inventory to ``blockID``

### client:sethacks

```lua
client:sethacks(table: hacks)
```

Controls the client's hacks.

The table should look like this:

```lua
local hacks = {
    ["jumpheight"] = int: jumpHeight,
    ["thirdperson"] = bool: allowThirdPerson,
    ["spawncontrol"] = bool: allowSpawnControl,
    ["speeding"] = bool: allowSpeeding,
    ["noclip"] = bool: allowNoclip,
    ["flying"] = bool: allowFlying
}
```

### client:setheldblock

```lua
client:setheldblock(int: blockId, bool: force)
```

Forces the client to hold a ``blockId``, and even locks it if ``force`` is true. For more information, please look at [CPE HeldBlock](https://wiki.vg/Classic_Protocol_Extension#HeldBlock)

### client:setorderblock

```lua
client:setorderblock(int: blockId, int: slot)
```

Allows the server to edit the block list. For more information, please look at [CPE InventoryOrder](https://wiki.vg/Classic_Protocol_Extension#InventoryOrder)

### client:settexpack

```lua
client:settexpack(string: texPackLink)
```

Sends the client a new texture pack to download and use.

### client:setvelocity

```lua
client:setvelocity(Vector: vel)
```

Applies velocity to a client.

## Functions

### client:gotoworld

```lua
client:gotoworld(World: world)
```

Sends the client to a given world.

### client:reload

```lua
client:reload()
```

Reloads the client.

### client:spawn

```lua
client:spawn()
```

Spawns the client.

### client:despawn

```lua
client:despawn()
```

Despawns the client.


### client:sendbulk

```lua
client:sendbulk(BulkBlockUpdate: bulk)
```

Sends the client a BulkBlockUpdate.

### Cuboid: client:newcuboid

```lua
client:newcuboid()
```

Creates and returns a new cuboid object for a client.

!!! note
    There is a hard limit of 16 cuboids per player.

### client:plmesg 

```lua
client:plmesg(int: arg1, string: arg2)
```

Sends a plugin message to the player.

!!! warning
    This feature is ClassiCube exclusive.
    I have yet to fully understand this feature of CC.

### client:update

```lua
client:update()
```

Updates the client for everyone else.

### client:teleport

```lua
client:teleport(Vector: position, Angle: rotation)
```

Teleports the client.

### client:kick

```lua
client:kick(string: reason)
```

Kicks the client with a given reason.

### client:chat

```lua
client:chat(string: message)
```

Sends a chat message to the client.