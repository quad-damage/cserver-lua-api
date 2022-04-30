# onTick

Fired every tick.

!!! warning
    It's not a good idea to do intensive tasks in ``onTick``.
    Think twice as to what you're throwing in here!

## Usage

```lua
function onTick(int: delta)
    print(string.format("Took %s since last tick.", delta))
end
```

