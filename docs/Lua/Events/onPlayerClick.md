# onPlayerClick

Fired every time the player clicks.

## Usage

```lua
function onPlayerClick(Client: clientObj, PlayerClickEvent: playerClickEvent)
    client:chat(string.format("You clicked at %s button %s", playerClickEvent.position, playerClickEvent.button))
end
```

## Player Click Event

| Field     | Type      | Description                                               |
|-----------|-----------|-----------------------------------------------------------|
| angle     | Angle     | Angle the client had when clicked.                        |
| position  | Vector    | Position of the block that was clicked or (-1, -1, -1)    |
| target    | Client    | The player that was clicked on, or nil if none.           |
| action    | bool      | True = Pressed, False = Released                          |
| face      | int       | Face of the block that was clicked or 255.                |
| button    | int       | Button which was used to click.                           |

| Button ID | Button Name  |
|-----------|--------------|
| 0         | Left Click   |
| 1         | Right Click  |
| 2         | Middle Click |
