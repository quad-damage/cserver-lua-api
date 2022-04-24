# Vector

!!! note
    Note that this class represents both ``Float Vectors`` and ``Short Vectors``.

## Fields

### number: x

```lua
vector.x
```

### number: y

```lua
vector.y
```

### number: z

```lua
vector.z
```

## Functions

### bool: vector:iszero

```lua
vector:iszero()
```

Returns whether or not the vector is (0, 0, 0)

### vector:scale

```lua
vector:scale(float: factor)
```

```lua
vector:scale(short: factor)
```

Scales up the vector by the ``factor``.

### vector:set

```lua
vector:set(float: X, float: Y, float: Z)
```

```lua
vector:set(short: X, short: Y, short: Z)
```

Sets the fields of a vector.

### vector:get

```lua
vector:get()
```

Returns the fields of the vector

Example:

```lua
local function command_func(caller, args)
    local position = caller:getpositiona()
    
    local x, y, z = position:get()

    return string.format("Your position: %s %s %s", x, y, z)
end
```