# preReload

Fires before the script reloads.

## Usage

```lua
function preReload()
    print("Script is about to reload.")
    -- Good place to remove any commands you had, otherwise they stay in memory.
end
```
