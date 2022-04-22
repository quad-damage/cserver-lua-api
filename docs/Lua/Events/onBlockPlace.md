# onBlockPlace

Fired when a client places a block.

## Usage

```lua
function onBlockPlace(client, position, id)
    print(string.format("Player %s has placed id %s at %s", client:getname(), id, position))
end
```
