# onConnect

Fired on an incoming connection.

!!! warning
    The client is not fully initialized at this point. For a more complete client, use [onHandshake](/Lua/Events/onHandshake)

## Usage

```lua
function onConnect(client)
    client:chat(string.format("Incoming connection: %s", client:getaddr()))
end
```

