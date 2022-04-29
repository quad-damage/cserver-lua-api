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

### vector:normalize

```lua
vector:normalize()
```

```lua
vector:normalize(Vector: dstVec)
```

Returns or writes the normalized vector.

### vector:magnitude

```lua
vector:magnitude()
```

Returns the magnitude of the vector.

### vector:cross

```lua
vector:cross(Vector: bVec)
```

```lua
vector:cross(Vector: bVec, Vector: dstVector)
```

Returns or writes the cross product of 2 vectors.

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
    local position = caller:getposition()
    
    local x, y, z = position:get()

    return string.format("Your position: %s %s %s", x, y, z)
end
```

### vector:toshort()

```lua
vector:toshort()
```

Transforms a float vector into a short vector.

### vector:tofloat()

```lua
vector:tofloat()
```

Transforms a short vector into a float vector.