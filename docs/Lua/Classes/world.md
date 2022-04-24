# World

## Getters 

### string: world:getname

```lua
world:getname()
```

Returns the worlds's name.

### bool: world:getspawn

```lua
world:getspawn(Vector: position, Angle: rotation)
```

Writes the world's spawn into ``position`` and ``rotation``.

### Vector: world:getspawna

```lua
world:getspawna()
```

Returns the world's spawn.

### int: world:getoffset

```lua
world:getoffset(Short Vector: ShortVector)
```

Return's the 1D location of the block at ``ShortVector``.

Equation: ``(((ShortVector.y) * World.Length + (ShortVector.z)) * World.Width + (ShortVector.x))``

### bool: world:getdimensions

```lua
world:getdimensions(Vector: dimensions)
```

Writes the world's dimensions into ``dimensions``.

### Vector: world:getdimensionsa

```lua
world:getdimensionsa()
```

Returns the world's dimensions.

### int: world:getblock

```lua
world:getblock(Vector: pos)
```

Returns the block at ``pos``.

### bool: world:getenvcolor

```lua
world:getenvcolor(EColor: colorType, Color3: color)
```

Writes the world's ``colorType`` into ``color``.

### Color3: world:getenvcolora

```lua
world:getenvcolora(EColor: colorType)
```

Returns the world's ``colorType``.

| Index | Name                  |
|-------|-----------------------|
|   0   | WORLD_COLOR_SKY       |
|   1   | WORLD_COLOR_CLOUD     |
|   2   | WORLD_COLOR_FOG       |
|   3   | WORLD_COLOR_AMBIENT   |
|   4   | WORLD_COLOR_DIFFUSE   |

### int: world:getenvprop

```lua
world:getenvprop(EProp: property)
```

Returns the value of a world's EnvProp.

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

### int world:getweather

```lua
world:getweather()
```

Returns the world's weather.

| Index | Name                  |
|-------|-----------------------|
|   0   | WORLD_WEATHER_SUN     |
|   1   | WORLD_WEATHER_RAIN    | 
|   2   | WORLD_WEATHER_SNOW    |

### string: world:gettexpack

```lua
world:gettexpack()
```

Returns the world's texture pack.

### int: world:getplayercount

```lua
world:getplayercount()
```

Returns the world's playercount.

### bool world:isready

```lua
world:isready()
```

Returns whether or not is world is ready to be played on.

### bool world:isinmemory

```lua
world:isinmemory()
```

Returns whether or not is world is in memory.

### bool world:ismodified

```lua
world:ismodified()
```

Returns whether or not the world has been modified since loading.

### bool: world:haserror

```lua
world:haserror()
```

Retruns whether or not the world has encountered an error.

### EWorldError, EWorldExtra: world:poperror

```lua
world:poperror()
```

Retruns more information about the error the world has encountered.

EWorldError:

| Index | Description                   |
|-------|-------------------------------|
|   0   | WORLD_ERROR_SUCCESS           |
|   1   | WORLD_ERROR_IOFAIL            |
|   2   | WORLD_ERROR_COMPR             |
|   3   | WORLD_ERROR_INFOREAD          |
|   4   | WORLD_ERROR_DATAREAD          |
|   5   | WORLD_ERROR_INMEMORY          |

EWorldExtra:

| Index | Description                   |
|-------|-------------------------------|
|   0   | WORLD_EXTRA_NOINFO            |
|   1   | WORLD_EXTRA_UNKNOWN_DATA_TYPE |
|   2   | WORLD_EXTRA_IO_OPEN           |
|   3   | WORLD_EXTRA_IO_WRITE          |
|   4   | WORLD_EXTRA_IO_RENAME         |
|   5   | WORLD_EXTRA_COMPR_INIT        |
|   6   | WORLD_EXTRA_COMPR_PROC        |

## Setters

### world:setspawn

```lua
world:setspawn(Vector: pos, Angle: rot)
```

Sets the world's spawn.

### world:setblock

```lua
world:setblock(Short Vector: pos, int: blockId)
```

Sets a block in the world.

!!! warning
    This only sets the block server-side.
    Use ``setblocknat`` to set and network the new block.

### world:setblocknat

```lua
world:setblocknat(Short Vector: pos, int: blockId)
```

Sets a block in the world and networks it.

### world:setenvcolor

```lua
world:setenvcolor(EColor: colorType, Color3: color)
```

Sets a world's env color. For more information, please look at [CPE EnvSetColor](https://wiki.vg/Classic_Protocol_Extension#EnvSetColor_Packet)

| Index | Name                  |
|-------|-----------------------|
|   0   | WORLD_COLOR_SKY       |
|   1   | WORLD_COLOR_CLOUD     |
|   2   | WORLD_COLOR_FOG       |
|   3   | WORLD_COLOR_AMBIENT   |
|   4   | WORLD_COLOR_DIFFUSE   |

### world:setenvprop

```lua
world:setenvprop(EProp: property, int: value)
```

Sets a world's EnvProp. For more information, please look at [CPE SetMapEnvProp](https://wiki.vg/Classic_Protocol_Extension#SetMapEnvProperty_packet)


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

### world:setweather

```lua
world:setweather(EWeather: weather)
```

Sets the world's weather.

| Index | Name                  |
|-------|-----------------------|
|   0   | WORLD_WEATHER_SUN     |
|   1   | WORLD_WEATHER_RAIN    | 
|   2   | WORLD_WEATHER_SNOW    |

### world:settexpack

```lua
world:settexpack(string: texPackLink)
```

Sets the world's default texture pack.

### world:setinmemory

```lua
world:setinmemory(bool: inMemory)
```

-

### world:setignoremod

```lua
world:setignoremod(bool: ignoreMod)
```

-

## Functions

### world:update

```lua
world:update()
```

Updates the world for every client playing on it.

### world:generate

```lua
world:generate(string: generatorName)
```

```lua
world:generate(string: generatorName, int seed)
```

(Re)generates the world.

### world:iterplayers

```lua
world:iterplayers(func: ITERATE_FUNCTION(Client client))
```

Iterates through the clients of a world, passing them to ``ITERATE_FUNCTION``

### world:remove

```lua
world:remove()
```

Removes the world from the worlds list.

### world:unload

```lua
world:unload()
```

Unloads the world from memory.

### world:save

```lua
world:save()
```

Saves the world to disk.

### world:load

```lua
world:load()
```

Loads the world disk.