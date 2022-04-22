# onRotate

Fired when a client rotates.

!!! warning
    It's not a good idea to do intensive tasks in ``onRotate``.
    Think twice as to what you're throwing in here!

## Usage

```lua
function onRotate(client)
    print(string.format("Client %s has rotated!", client:getname()))
end 
```

