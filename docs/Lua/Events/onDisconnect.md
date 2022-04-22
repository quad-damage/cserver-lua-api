# onDisconnect

Fired when a client disconnects.

## Usage

```lua
function onDisconnect(client, reason)
    print(string.format("Client %s has disconnected because \"%s\"", client:getname(), reason))
end
```
