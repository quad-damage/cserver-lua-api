# onWorldLoaded

Fired when a world gets loaded from file.

## Usage

```lua
function onWorldLoaded(World: world)
    print(string.format("A new world has been loaded: %s", world:getname()))
end
```
