# onWorldUnloaded

Fired when a world gets unloaded from memory.

## Usage

```lua
function onWorldUnloaded(World: world)
    print(string.format("A world has been unloaded: %s", world:getname()))
end
```
