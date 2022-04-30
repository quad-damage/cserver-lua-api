# onMessage

Fired when the client sends a message.

!!! warning
    This event also takes into account commands.

## Usage

```lua
function onMessage(Client: clientObj, EMsgType: type, string: message)
    print(string.format("Client %s has said \"%s\" in EMsgType %s", client:getname(), message, msgType))

    -- Protip: You can change the EMsgType here.
    return type, message
end
```

| Index | Name                          |
|-------|-------------------------------|
| 0     | MESSAGE_TYPE_CHAT             |
| 1     | MESSAGE_TYPE_STATUS1          |
| 2     | MESSAGE_TYPE_STATUS2          |
| 3     | MESSAGE_TYPE_STATUS3          |
| 11    | MESSAGE_TYPE_BRIGHT1          |
| 12    | MESSAGE_TYPE_BRIGHT2          |
| 13    | MESSAGE_TYPE_BRIGHT3          |
| 100   | MESSAGE_TYPE_ANNOUNCE         |
| 101   | MESSAGE_TYPE_BIGANNOUNCE      |
| 102   | MESSAGE_TYPE_SMALLANNOUNCE    |