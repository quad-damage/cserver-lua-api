# onMove

Fired when a client moves.

!!! warning
    It's not a good idea to do intensive tasks in ``onMove``.
    Think twice as to what you're throwing in here!

## Usage

```lua
function onMove(Client: clientObj)
    print(string.format("Client %s has moved!", client:getname()))
end 
```

