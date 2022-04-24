# onWorldAdded

Fired when a world gets added to the world list.

## Usage

```lua
function onWorldAdded(World: world)
    print(string.format("A new world has been added: %s", world:getname()))
end
```
