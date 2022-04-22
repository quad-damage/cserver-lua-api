# onUserTypeChange

Fired when a user's type changes.

!!! note
    Seems to be used when a player gets opped or deopped.

## Usage

```lua
function onUserTypeChange(client)
    client:chat(string.format("Your user type has changed OP: %s", client:isop()))
end
```
