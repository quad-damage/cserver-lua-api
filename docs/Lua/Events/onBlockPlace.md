# onBlockPlace

Fired when a client places a block.

!!! note
    Returning ``false`` here will disallow the client from placing the block.

## Usage

```lua
function onBlockPlace(Client: clientObj, Vector: position, int: blockId)
    print(string.format("Player %s has placed id %s at %s", client:getname(), id, position))
end
```
