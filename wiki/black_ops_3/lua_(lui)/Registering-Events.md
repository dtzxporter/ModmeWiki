# Registering Events

## Registering an event callback
For standard events like the menu loading, we can use a function to register events. Below is a working callback:
``` lua
local function MenuLoadedEvt(Sender, EventArgs)
      -- Do something (Sender = Hud, EventArgs = Arguments for event)
end

-- The event name and callback
Hud:registerEventHandler("menu_loaded", MenuLoadedEvt)
```
Each element has a specific set of events. In addition, event arguments change per-event.