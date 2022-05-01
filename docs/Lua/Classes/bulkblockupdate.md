# BulkBlockUpdate

## Functions

### BulkBlockUpdate:setautosend

```lua
bulkblockupdate:setautosend(bool: autoSend)
```

If true, BulkBlockUpdate packet will be sent when it overflows(over 256 calls to ``bulkblockupdate:add``).

### BulkBlockUpdate:setworld

```lua
bulkblockupdate:setworld(World: worldObj)
```

Sets the World of the BulkBlockUpdate.

### BulkBlockUpdate:push

```lua
bulkblockupdate:push()
```

Pushes the BulkBlockUpdate to its world.

### BulkBlockUpdate:add

```lua
bulkblockupdate:add(int: offset, int: blockId)
```

```lua
bulkblockupdate:add(int: offset1, int: blockId1, int: offset2, int: blockId2 ...)
```

```lua
bulkblockupdate:add(table: {int: offset1, int: blockId1, int: offset2, int: blockId2 ...})
```

Adds the block at offset to the BulkBlockUpdate object.

Also takes tables, as well as multiple arguments.

