# onHeldBlockChange

Fired when a client changes the block held in his hand.

## Usage

```lua
function onHeldBlockChange(Client: clientObk, int: newBlockID, int: oldBlockID)
    print(string.format("Client %s has just swapped from %s to %s", client:getname(), oldBlockID, newBlockID))
end
```
