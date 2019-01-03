# Your First Custom Control Widget

## Creating a custom control
Creating a custom control is useful when you will have a fairly complex hud with multiple segments. For instance in-game, the ammo information is usually it's own control with various other children controls. For the sake of this tutorial we will be using the namespace `CoD`.

## Setting up the control
First, all controls should extend the base `UIElement` this defines most of the usual properties for you:
``` lua
CoD.TestControl = InheritFrom(LUI.UIElement)
```
This tells the game to make our control apart of a `UIElement` so that we can easily extend it's usage.

## Defining a control base
To customize the control we need to provide a `new` function that will do the customization such as adding elements to it:
``` lua
CoD.TestControl = InheritFrom(LUI.UIElement)

function CoD.TestControl.new(HudRef, InstanceRef)
      local Elem = LUI.UIElement.new()
      Elem:setClass(CoD.TestControl)
      Elem.id = "TestControl"
      Elem.soundSet = "default"
      return Elem
end
```

## Customizing the control
Now that we have a `new` function we are free do manipulate the control. One of the most common things to do is add children controls to the element:
``` lua
CoD.TestControl = InheritFrom(LUI.UIElement)

function CoD.TestControl.new(HudRef, InstanceRef)
      local Elem = LUI.UIElement.new()
      Elem:setClass(CoD.TestControl)
      Elem.id = "TestControl"
      Elem.soundSet = "default"

      local TextChild = LUI.UIText.new(Elem, InstanceRef)
      TextChild:setLeftRight(true, true, 0, 0)
      TextChild:setTopBottom(true, true, 0, 0)
      TextChild:setText("Hello World!")

      Elem:addElement(TextChild)

      return Elem
end
```
This will add a text element to our control.

## Using our control
To use the control outside of its file, you must first include it in your zone:
``` php
rawfile,testcontrol.lua // File name and path
```
Next, you must `require` the script in the lua file you wish to use it from:
``` lua
require("testcontrol")
```
Finally to make an instance of your control you would use:
``` lua
local Control = CoD.TestControl.new(HudRef, InstanceRef)
```
Since we used `UIElement` as a base, you can use properties like margins and anchors on the element like anything else.