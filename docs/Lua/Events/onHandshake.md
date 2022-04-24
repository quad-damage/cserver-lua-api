# onHandshake

Fired on a handshake with a user.

!!! note
    Returning a World here will send the client to it.

## Usage

```lua
function onHandshake(client)
    client:chat(string.format("Welcome to the server, %s", client:getname()))
end
```
