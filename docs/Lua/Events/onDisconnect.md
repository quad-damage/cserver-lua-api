# onDisconnect

Fired when a client disconnects.

## Usage

```lua
function onDisconnect(Client: clientObj, String: reason)
    print(string.format("Client %s has disconnected because \"%s\"", client:getname(), reason))
end
```
