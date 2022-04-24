# onBlockDestroy

Fired when a client destroys a block.

## Usage

```lua
function onBlockDestroy(Client: client, Vector: position, int: id)
    print(string.format("Player %s has broken block at %s", client:getname(), position))
end
```

!!! warning
    ``id`` seems to always be 0.
