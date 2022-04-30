# command
Allows you to interact with users through / commands.

## Functions

### command.add

```lua 
command.add(string: COMMAND_NAME, 
            string: COMMAND_DESCRIPTION, 
            bitflag: COMMAND_PERMISSIONS, 
            func: COMMAND_FUNC(caller, args))
```

Registers a command.

The command permissions are:

| Flag           | Meaning                      |
|----------------|------------------------------|
| CMDF_NONE      | Everyone(including console)  |
| CMDF_OP        | OPs Only                     |
| CMDF_CLIENT    | Clients Only                 |
| CMDF_RESERVED0 | Reserved                     |
| CMDF_RESERVED1 | Reserved                     |
| CMDF_RESERVED2 | Reserved                     |

Strings returned by ``COMMAND_FUNC`` are sent to the caller.

!!! warning
    When a command is called from console, the caller will be nil.

### command.setalias

```lua 
command.setalias(string: COMMAND_NAME, string: COMMAND_ALIAS)
```

Registers an alias for an existant command.

!!! warning
    Aliases can only be 6 letters long! Anything over that gets ignored.


### command.remove

```lua 
command.remove(string: commandName)
```

Removes an existant command.

## Examples

```lua
allowHotReload(true)

local cmd_name = "testcmd"

local function testcmd(caller, args)
    caller:chat("Test command executed!")
    if(args ~= nil) then
        caller:chat(args)
    end

    return "End of function!"
end

function onStart()
    command.add(cmd_name, "Test Command", CMDF_NONE, testcmd)
    command.setalias(cmd_name, "test")
end

function preReload()
    command.remove(cmd_name)
end

function onStop()
	command.remove(cmd_name)
end
```

![Screenshot](/resources/testcmd.png)