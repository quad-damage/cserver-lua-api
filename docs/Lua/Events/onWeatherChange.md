# onWeatherChange

Fired when the weather in a world changes.

## Usage

```lua
function onWeatherChange(world)
    local weather_types = {
        [0] = "Sun",
        [1] = "Rain",
        [2] = "Snow"
    }
    print(string.format("Weather has changed in world %s to %s", world:getname(), weather_types[world:getweather()]))
end
```
