# onHandshake

Fired on a handshake with a user.

## Usage

```lua
function onHandshake(client)
    client:chat(string.format("Welcome to the server, %s", client:getname()))
end
```
