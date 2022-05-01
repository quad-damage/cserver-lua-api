# config

Allows interfacing with the config api.

## Functions

### Config: config.new 

```lua
config.new(table: params)
```

The ``params`` table holds general information about the config file.

| Parameter         | Description                               |
|-------------------|-------------------------------------------|
| name              | Name of the config.                       |
| items             | Table of items in the config.             |

!!! note
    Best practice is to name the config files using io.scrname()

The ``items`` table holds config elements in tables with the following structure:

| Parameter         | Description                               |
|-------------------|-------------------------------------------|
| name              | Name of the config item.                  |
| type              | ECType: Type of the config item.          |
| comment           | Comment for the config item.              |
| default           | Default value for the config item.        |

ECType:

| Config Type       |
|-------------------|
| CONFIG_TYPE_BOOL  |
| CONFIG_TYPE_INT32 |
| CONFIG_TYPE_INT16 |
| CONFIG_TYPE_INT8  |
| CONFIG_TYPE_STR   |

### string, string: config.error

```lua
config.error(configObj:poperror())
```

Returns the string representation of error codes returned by ``config:poperror()``.

## Examples

```lua
function onStart()
	mycfg = config.new{
		name = 'mycfg.cfg',
		items = {
			{
				name = 'my-key-i16',
				type = CONFIG_TYPE_INT16,
				comment = 'Signed short key',
				default = -1
			},
			{
				name = 'my-key-str',
				type = CONFIG_TYPE_STR,
				default = 'Wtf is that string?'
			},
			{
				name = 'my-key-bool',
				type = CONFIG_TYPE_BOOL,
				comment = 'No way it\'s a boolean!',
				default = true
			}
		}
	}

	mycfg:save(not mycfg:load())
	print('Config string:', mycfg:get('my-key-str'))
	print('Config bool:', mycfg:get('my-key-bool'))
	print('Config short:', mycfg:get('my-key-i16'))
end
```

![Screenshot](/resources/mycfg.png)