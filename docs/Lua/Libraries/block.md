# block
Creation and interaction with custom blocks.

## Functions

### Block: block.define

```lua
block.define(Table: blockDefinition)
```

Returns a new block with the defined parameters.

blockDefinition table structure:

| Parameter     | Description                                                   |
|---------------|---------------------------------------------------------------|
| name          | String: The name of your block.                               |
| fallback      | Int: ID of the fallback block(for vanilla clients).           |
| extended      | Boolean: Whether or not the block is extended.                |
| param         | Table: List of block parameters.                              |

For non-extended blocks, the follow params table is used:

| Parameter     | Description                                                       |
|---------------|-------------------------------------------------------------------|
| solidity      | EBlockSolidity: Collision mode for this block.                    |
| movespeed     | Byte: Speed modifier of the block. Look at DefineBlock [movespeed](https://wiki.vg/Classic_Protocol_Extension#DefineBlock_Packet) for more info |
| toptex        | Texture ID for the top of the block.                              |
| sidetex       | Texture ID for the side of the block.                             |
| bottomtex     | Texture ID for the bottom of the block.                           |
| transmitsLight| Whether or not this block allows sunlight to go through.          |
| walksound     | EBlockSounds: Sound the block makes when walked on.               |
| fullbright    | Whether or not this block affected by shadows.                    |
| shape         | 0 - Sprite; 1 -> 16 Height of the block.                          |
| drawType      | EBlockDrawTypes: The way the block is drawn client-side.          |
| fogdensity    | Density of fog while the client's camera is inside the block.     |
| fogR          | R Color of the fog while the client's camera is inside the block. |
| fogG          | G Color of the fog while the client's camera is inside the block. |
| fogB          | B Color of the fog while the client's camera is inside the block. |

For extended blocks, the following params table is used:

| Parameter     | Description                                                       |
|---------------|-------------------------------------------------------------------|
| solidity      | EBlockSolidity: Collision mode for this block.                    |
| movespeed     | Byte: Speed modifier of the block. Look at DefineBlock [movespeed](https://wiki.vg/Classic_Protocol_Extension#DefineBlock_Packet) for more info |
| toptex        | Texture ID for the top of the block.                              |
| lefttex       | Texture ID for the left side of the block.                        |
| righttex      | Texture ID for the right side of the block.                       |
| fronttex      | Texture ID for the front of the block.                            |
| backtex       | Texture ID for the back of the block.                             |
| bottomtex     | Texture ID for the bottom of the block.                           |
| transmitsLight| Whether or not this block allows sunlight to go through.          |
| walksound     | EBlockSounds: Sound the block makes when walked on.               |
| fullbright    | Whether or not this block affected by shadows.                    |
| minx          | Minimum X coordinate in pixels. Values between 0 and 15 allowed.  |
| miny          | Minimum Y coordinate in pixels. Values between 0 and 15 allowed.  |
| minz          | Minimum Z coordinate in pixels. Values between 0 and 15 allowed.  |
| maxx          | Maximum X coordinate in pixels. Values between 0 and 15 allowed.  |
| maxy          | Maximum Y coordinate in pixels. Values between 0 and 15 allowed.  |
| maxz          | Maximum Z coordinate in pixels. Values between 0 and 15 allowed.  |
| drawType      | EBlockDrawTypes: The way the block is drawn client-side.          |
| fogdensity    | Density of fog while the client's camera is inside the block.     |
| fogR          | R Color of the fog while the client's camera is inside the block. |
| fogG          | G Color of the fog while the client's camera is inside the block. |
| fogB          | B Color of the fog while the client's camera is inside the block. |

EBlockSolidity:

| Name          | Description                                                       |
|---------------|-------------------------------------------------------------------|
| BDSOL_WALK    | No collision(can walk through the block).                         |
| BDSOL_SWIM    | Liquid collision(can swim through the block: water, lava etc.)    |
| BDSOL_SOLID   | Block collision(can walk on the block).                           |

EBlockSounds:

| Name          |
|---------------|
| BDSND_NONE    |
| BDSND_WOOD    |
| BDSND_GRAVEL  |
| BDSND_GRASS   |
| BDSND_STONE   |
| BDSND_METAL   |
| BDSND_GLASS   |
| BDSND_WOOL    |
| BDSND_SAND    |
| BDSND_SNOW    |

EBlockDrawTypes:

| Name          | Description                                                   |
|-------------------|-----------------------------------------------------------|
| BDDRW_OPAQUE      | Opaque block.                                             |
| BDDRW_TRANSPARENT | Transparent with face culling of same neighbour.          |
| BDDRW_TRANSPARENT2| Transparent with no face culling of same neighbour.       |
| BDDRW_TRANSLUCENT | Transparent and shaded by texture(water, ice etc.)        |
| BDDRW_GAS         | Fully transparent(air).                                   |

### bool: block.isvalid

```lua
block.isvalid(Number: blockId)
```

Returns whether or not the block is valid.

### int: block.fallbackfor

```lua
block.fallbackfor(Number: blockId)
```

Returns the fallback id for the block.

### BulkBlockUpdate: block.bulk

```lua
block.bulk()
```

```lua
block.bulk([World: worldObj, bool: autoSend])
```

Creates a new BulkBlockUpdate object. If given, will automatically set the world and/or autoSend.