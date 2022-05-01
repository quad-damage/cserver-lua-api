# group
Interaction with the groups system.

## Functions 

### int: group.add

```lua
local groupId = group.add(string: name, int: rank)
```

Adds a new group, returning it's id. Lower-number ranks are listed before higher-number ranks.

### bool: group.remove

```lua
group.remove(int: groupId)
```

Removes a group, returning whether or not it was sucessful.

### string, int: group.getinfo

```lua
local groupName, groupRank = group.getinfo(int: groupId)
```

Returns general information about a group.