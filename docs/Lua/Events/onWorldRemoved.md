# onWorldRemoved

Fired when a world gets removed to the world list.

## Usage

```lua
function onWorldRemoved(World: world)
    print(string.format("A world has been removed: %s", world:getname()))
end
```
