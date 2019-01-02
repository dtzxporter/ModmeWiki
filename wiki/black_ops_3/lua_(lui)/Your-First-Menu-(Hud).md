1.  Creating your first menu in Lua
For the sake of this tutorial we will be creating a hud that works with a `Custom Zombies Map` however, the mechanics are similar.

1.  The starting function
In LUI, menus are registered under the `LUI.createMenu` namespace. This exposes your menu to the game and allows it to be used with `OpenLUIMenu("Name")`. Below is the base function:

function LUI.createMenu.T7Hud_zm_factory(Instance)

end

We are going to be using the T7Hud_zm_factory menu as an override, meaning our hud file should also be named `t7hud_zm_factory.lua`

1.  Creating the hud itself
To create the hud, we must tell the game to allocate one for us using:

function LUI.createMenu.T7Hud_zm_factory(Instance)
      local Hud = CoD.Menu.NewForUIEditor("T7Hud_zm_factory")

      return Hud
end

This makes the base hud that we will add our controls to.

1.  Setting up the hud
The basic hud should cover the whole screen, other types like popups can have variable sizes. For our usage, we will cover the screen:

function LUI.createMenu.T7Hud_zm_factory(Instance)
      local Hud = CoD.Menu.NewForUIEditor("T7Hud_zm_factory")

      -- Set the current sound profile
      Hud.soundSet = "HUD"
      -- Set the owner of our hud to the root 'instance'
      Hud:setOwner(Instance)
      -- Set the anchors (Left: True, Right: True, LeftMargin: 0, RightMargin: 0)
      Hud:setLeftRight(true, true, 0, 0)
      -- Set the anchors (Top: True, Bottom: True, TopMargin: 0, BottomMargin: 0)
      Hud:setTopBottom(true, true, 0, 0)
      -- Play the opening sound (From 'HUD' profile)
      Hud:playSound("menu_open", Instance)

      return Hud
end

This is a typical fullscreen hud setup, we have a hud that stretches to the window size and also play the opening sound at the time of loading.

1.  Adding a control
Adding a control to the hud is easy, but you should be careful to reference your element so we can clean up properly later. The following will add a control:

function LUI.createMenu.T7Hud_zm_factory(Instance)
      local Hud = CoD.Menu.NewForUIEditor("T7Hud_zm_factory")

      -- Set the current sound profile
      Hud.soundSet = "HUD"
      -- Set the owner of our hud to the root 'instance'
      Hud:setOwner(Instance)
      -- Set the anchors (Left: True, Right: True, LeftMargin: 0, RightMargin: 0)
      Hud:setLeftRight(true, true, 0, 0)
      -- Set the anchors (Top: True, Bottom: True, TopMargin: 0, BottomMargin: 0)
      Hud:setTopBottom(true, true, 0, 0)
      -- Play the opening sound (From 'HUD' profile)
      Hud:playSound("menu_open", Instance)

      -- Make a new text element
      Hud.TestText = LUI.UIText.new(Hud, Instance)

      -- Set properties
      Hud.TestText:setLeftRight(true, false, 20, 250)
      Hud.TestText:setTopBottom(true, false, 20, 50)
      Hud.TestText:setText("Hello World!")

      Hud:addElement(Hud.TestText)  -- Add the control to the hud

      return Hud
end


1.  Cleaning up properly
Now that we added a control, it is important to properly clean up the control after, below, we will register an event for the menu closing and then close our children controls:

function LUI.createMenu.T7Hud_zm_factory(Instance)
      local Hud = CoD.Menu.NewForUIEditor("T7Hud_zm_factory")

      -- Set the current sound profile
      Hud.soundSet = "HUD"
      -- Set the owner of our hud to the root 'instance'
      Hud:setOwner(Instance)
      -- Set the anchors (Left: True, Right: True, LeftMargin: 0, RightMargin: 0)
      Hud:setLeftRight(true, true, 0, 0)
      -- Set the anchors (Top: True, Bottom: True, TopMargin: 0, BottomMargin: 0)
      Hud:setTopBottom(true, true, 0, 0)
      -- Play the opening sound (From 'HUD' profile)
      Hud:playSound("menu_open", Instance)

      -- Make a new text element
      Hud.TestText = LUI.UIText.new(Hud, Instance)

      -- Set properties
      Hud.TestText:setLeftRight(true, false, 20, 250)
      Hud.TestText:setTopBottom(true, false, 20, 50)
      Hud.TestText:setText("Hello World!")

      Hud:addElement(Hud.TestText)  -- Add the control to the hud

      -- Callback for the hud closing
      local function OnHudClose(Sender)
          Sender.TestText:close()  -- Close the element
      end

      -- Register the callback
      LUI.OverrideFunction_CallOriginalSecond(Hud, "close", OnHudClose)

      return Hud
end

By overriding the close function of the hud, it allows us to cleanup the elements we made earlier. By including this hud and overriding the factory hud file: `ui/uieditor/menus/hud/t7hud_zm_factory.lua` You will see the changes you made while opening a map like `The Giant` or a mod map.