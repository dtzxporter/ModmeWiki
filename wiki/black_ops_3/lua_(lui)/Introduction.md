# Introduction
Lua (LUI) Getting Started

Lua is a fairly simple language to learn, it's syntax is similar to python. However, the Lua implementation in Call of Duty Black Ops 3 (HavokScript) has slight differences which you'll need to be aware of. This tutorial will **NOT** go over how to script in Lua, you must learn that on your own! However, this will outline some of the key differences that you will need to follow.

## Requiring another script
In standard Lua, you can require another script using:

``` lua
-- Use the file in the folder 'a' named 'b.lua'
require("a/b.lua")
```
In BO3, you can still do this, however, the syntax is different:

``` lua
-- Use the file in the folder 'a' named 'b.lua'
require("a.b")
```

Basically, the paths are now '.' and you remove the trailing '.lua'. This functions the same as standard lua.

## Function scopes
Normally it's ok to declare global functions and variables in standard Lua without an issue. However, in BO3 unless otherwise stated. All variables and functions should be local:
``` lua
local function Hello()
      print("Hello world!")
end

local function Test()
      local Wins = ""
end
```

Otherwise, you may hit a random out of memory issue...

## Catching call exceptions
In BO3 Lua, you can catch a function for errors, but you must wrap the call...
``` lua
function test()
      <something that errors>
end

if pcall(test) then
      success
else
      failed
end
```

Wrapping the call in a `pcall` will prevent errors from halting the game.

## LUI Specific Information
Below is a list of LUI specific data for use with the other tutorials, you should be familiar with these concepts:

  * Stock menu size: 1280x960 (Up-scaled and Down-scaled as needed).
  * LUI is the root namespace of elements.
  * UIElement is the root of all elements and can house other controls.
  * UIText element's font size is determined by the height of the control alone.
  * UIImage element's image will stretch to fit the control size.
  * All controls support AnchorLeft, AnchorRight, AnchorTop, and AnchorBottom for responsive layout design.
  * A `Widget` is a collection of the base elements into a custom control. Widgets are **not stock** elements.
  * To include a custom menu, you use `#precache("lui_menu", "<name of lua file>")` in script files.
  * To use a menu property name, you must use `#precache("lui_menu_data", "property name")` in script files.
  * To use a LUI event name, you must use `#precache("eventstring", "event name")` in script files.
  * To include a file, you use `rawfile,<lua file path>.lua` the same as any other file.
  * With linker, you can include pre-compiled Lua files with `*.luac` extensions.
  * Only syntax errors are caught at compile-time, if an error occurs in-game, this will break all existing menus.
  * For custom maps, your hud is going to override `T7Hud_zm_factory`.

  _Contributers:_
  - DTZxPorter