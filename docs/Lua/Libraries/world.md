# world
Allows you to interact with the world.

## Functions

### World: world.create

```lua 
world.create(string: worldName, Short Vector: worldDimensions)
```

Creates a new world.

### World: world.getbyname

```lua 
world.getbyname(string: worldName)
```

Returns a World object by its name.

### world.iterall

```lua
World.iterall(func: ITERATE_FUNCTION(World: worldObj))
```

Iterates through all worlds, passing them to ``ITERATE_FUNCTION()``. 