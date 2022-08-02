# Botway-Lua

> Lua client package for Botway.

## Installation

```bash
luarocks install botway-lua
```

## Usage

> this is an example of botway discord lua template

```lua
local new_client = require "lacord.x.client".new
local bot_config = require "botway-lua"
local bot = new_client(bot_config.GetToken())

bot.events.MESSAGE_CREATE:listen(function(ctx)
    local msg = ctx.event

    if not msg.author.bot and msg.content == "Hi" then
        bot.api:create_message(msg.channel_id, {
            content = "Hello, world! 🌚"
        })
    end
end)

bot:run()
```
