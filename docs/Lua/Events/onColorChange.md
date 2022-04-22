# onColorChange

Fired when an EnvColor in a world changes.

## Usage

```lua
function onColorChange(world)
    print(string.format("An EnvColor has changed in world %s", world:getname()))
end
```
