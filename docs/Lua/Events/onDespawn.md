# onDespawn

Fired when a client despawns.

## Usage

```lua
function onDespawn(Client: clientObj)
    print(string.format("Player %s has despawned!", client:getname()))
end
```
