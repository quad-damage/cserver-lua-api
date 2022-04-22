# client
Allows general interaction with clients.

A client is a player or a bot.

## Functions 

### client.getbyid

```lua 
client.getbyid(int: CLIENT_ID)
```

Returns a Client object by its id.

### client.getbyname

```lua 
client.getbyname(string: CLIENT_NAME)
```

Returns a Client object by its name.

### client.getcount

```lua
client.getcount(EClientState: CLIENT_STATE)
```

Returns the number of clients in a given EClientState

| Name                  | Description                   |
|-----------------------|-------------------------------|
| CLIENT_STATE_INITIAL  | Player just connected         |
| CLIENT_STATE_MOTD     | Player is receiving the map   |
| CLIENT_STATE_INGAME   | Player is in game             |

### client.iterall

```lua
client.iterall(func: ITERATE_FUNCTION(Client: client))
```

Iterates through all clients, passing them to ``ITERATE_FUNCTION()``. 

### client.newbot

```lua
client.newbot()
```

This function does nothing as of 23/4/2022 at 02:13 GMT+3