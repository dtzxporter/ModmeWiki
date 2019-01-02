1.  Adding perk slots to a Soe Hud Base
Adding perks to the hud with as little modification as possible will allow you to add custom perks while maintaining the original look and feel of the hud.

1.  Preparing your base file
First, you must open up your `t7hud_zm.lua` base file and find the following line:

require("ui.uieditor.widgets.HUD.ZM_Perks.ZMPerksContainer")

You must **remove** this line, as we will be including a custom one later.

Next, navigate to the following function:

function LUI.createMenu.T7Hud_zm(InstanceRef)

And find the line after the `PreLoadCallback` function. We are going to insert the following code below **under** that function call:

      -- Make sure that the list was not already setup, we must include the stock perks as well!
      if not CoD.ZMPerks then
          -- Add our perks (hudItems.perks.key = imageName) (sync with csc clientuimodel)
          CoD.ZMPerks =
          {
              additional_primary_weapon = "specialty_three_guns_zombies",
              dead_shot = "specialty_ads_zombies",
              dive_to_nuke = "specialty_divetonuke_zombies",
              doubletap2 = "specialty_doubletap_zombies",
              juggernaut = "specialty_juggernaut_zombies",
              marathon = "specialty_marathon_zombies",
              quick_revive = "specialty_quickrevive_zombies",
              sleight_of_hand = "specialty_fastreload_zombies",
              tombstone = "specialty_tombstone_zombies",
              widows_wine = "specialty_widows_wine_zombies"
          }
      end
      
      -- Include the new perk container, and resume normal widget usage!
      require("ui.uieditor.widgets.hud.customperks")


1.  Getting the custom container
Download the following patched container: [[CustomPerks|https://mega.nz/#!BFBRjTAQ!O8mtaNPGX3s686IM47j_UWfhoRmZED4FzzhgAgyDSZA]]. You must place the downloaded file to:

share/raw/ui/uieditor/widgets/hud/customperks.luac

Finally open up your maps zone file and add the following line to include the custom container:

rawfile,ui/uieditor/widgets/hud/customperks.luac


NOTE: The custom container must end in *.luac because it is a precompiled file!

1.  Final notes
Your hud modification is now complete and you may add as many slots as you like. You must make sure to register the perks in csc though as well just like the stock perks. See `_zm_perks.gsh` for the existing perk slot names.