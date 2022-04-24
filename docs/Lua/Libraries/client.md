# client
Allows general interaction with clients.

A client is a player or a bot.

## Functions 

### Client: client.getbyid

```lua 
client.getbyid(int: CLIENT_ID)
```

Returns a Client object by its id.

### Client: client.getbyname

```lua 
client.getbyname(string: CLIENT_NAME)
```

Returns a Client object by its name.

### int: client.getcount

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

### Client: client.newbot

```lua
client.newbot()
```

Returns a new Client object.

Example:

```lua
bot_client = client.newbot()
bot_client:gotoworld(world.getbyname('world'))
bot_client:teleport(vector.float(1, 3, 3), angle(7, 0))
bot_client:spawn()
```