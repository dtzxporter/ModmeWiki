# Creating a Basic Zombie Map

This requires you to have a working Mod Tools installation. See the relevant tutorial for installing them [[here|http://phabricator.aviacreations.com/w/world_at_war/installing_the_modtools/]].

> **NOTE:** `root` refers to your World at War installation path. If you got it from Steam, it will be in `C:\Program Files (x86)\Steam\steamapps\common\Call of Duty World at War\`, or if you installed Steam elsewhere, go there. If you have a disc install, it will be in `C:\Program Files (x86)\Activision\Call of Duty World at War\`.  

## Script Placers

In early days of zombie modding, setup files would have to be placed manually, but now most of that is done for you in the several script placers available. I highly recommend [Script Placer Z](http://tododdd). Requires registration. 

Right click on the .exe and click "Run as Administrator". For the sake of the tutorial, I'll refer to the map name as `tutorialmap`, obviously you can call your map whatever you want, and choose whichever features you like. It will create a small map that contains most things you need such as zones, spawners, barricades, mystery box, teleporters, etc. You can add these manually, but it's not recommended.

> **NOTE:** Modme may create a script placer that does not need registration in the future if we feel like it.
  
## Radiant

Radiant is the level editor used by all Call of Duty games. 

Open the Modtools Launcher which can be found at `root\bin\Launcher.exe`. This is a program that manages the process of creating and compiling a map. Click the button on the left that says "Radiant".

It may take a few seconds to load. You will be prompted to ask for a project file - locate `codwaw.prj` in the `\bin\` folder. You only have to do this once. Click Open, and Radiant will open the `root\map_source` folder. Locate you map - in the tutorial's case, `tutorialmap.map`. It should look something like this:

{F3279}

## Icons

For now I'll only explain these few icons.

{F3283, size=full, float} Open and Save

{F3285, size=full, float} Flip on X/Y/Z axis

{F3287, size=full, float} Rotate on X/Y/Z axis

> **NOTE:** The Z-axis is the vertical axis in the CoD engine.

To toggle the view in the 2D window, press `Ctrl-Tab`. It will cycle between top/side/front views. To move the grid, right-click and drag. Scroll in/out to zoom.

To look around in the 3D window, right click on it and drag forwards or backwards. To move left/right/up/down, hold `Ctrl` and do the same. To look around without moving, hold `Ctrl+Shift` and drag. 

To create a brush, left-click on the 2D grid and drag in any direction (be sure to press `Esc` once or twice to deselect anything first). Assign a texture to it by selecting a texture in the texture window in the bottom right. To extend or shrink it, left-click and hold just to the side of the brush and drag. Remember you can toggle the 2D view to extend or shrink the brush on a different axis. To move it, left-click and hold on the brush and drag. Creating brushes must be done in the 2D window, but modifying and moving it can be done in both 2D and 3D windows.

To select a brush or entity, hold `Shift` and left-click in either the 2D or 3D window. If you click the 2D window, you may involuntarily select a different brush, such as the light grid volume surrounding the map. Don't worry about this, just deselect and try again in the 3D window. Alternatively, you can press `F` on the keyboard which brings up a list called Filters, from which you can filter out things you don't want to see. This doesn't delete anything, nor does it exclude them in the compiling process.

To select individual faces of a brush, hold `Shift+Ctrl` and left-click.


## Creating Rooms

This map will pretty much work as it is, but I'm going to add an extra room to the map for demonstration. To do this, create 3 brushes outlining the room. I'll just be making a simple room next to the already existing smaller room.

You will need to extend the ceiling to cover the new room. Click on the ceiling brush and extend it.

Here's an action shot:

{F3289}

Don't worry if it doesn't look exactly the same.

This step is important: You need to extend the `Light Grid Volume`, that surrounds the existing building, to contain your new room. Simply select and extend it. You will also need to do this for the skybox. If you zoom out enough in the 3D view, you'll see a huge `Caulk` box surrounding the map. The inside faces of these brushes are the skybox. Select and extend the brushes so your map is surrounded. Be careful not to leave holes in the skybox.

Now we'll extend the playable area to include our new room. If you move your 3D view near the ceiling, you'll notice a large brush with the word `Trig` repeating on it. Press `N` on the keyboard - this will bring up the `Entity` window. You should see this: 

{F3291}

Those boxes with text in them are called `Key-Value Pairs` (or KVP for short). The playable area has the KVP `targetname` | `playable_area`. Select it and extend it to cover your new room.

## Doors

To add the door, we must add a gap in the brush that separates the two rooms. One way of doing this is to copy the brush by pressing `Space` with the brush selected. There are other ways of doing this but I'll stick with this for now. I then shrunk the two brushes and moved them into place, like so: 

{F3293}

You'll notice the thin faces of the two brushes have a `Caulk` texture. Just select the wall texture you're using with both brushes selected and it will apply it to all faces. 

Because we're adding a moving door, we can't just add a normal brush for the door - it needs to be a `script_brushmodel`. To make this, right-click in the 2D window and go to `script`>`brushmodel`, like so:

{F3295}

You'll need to add a KVP to this brush. Open the Entity window with `N` and add a new KVP, with key/value `spawnflags`|`1`. This is required for doors. If you want your door to move when it's purchased, you will also need to add `script_vector`|`x y z`, replacing the x/y/z with the number of units you want it to move along the respective axis. I want mine to move `-100` units on the x-axis, so I'll make the KVP `script_vector`|`-100 0 0`. (If I wanted it to move in the opposite direction, it would be a value of 100. If I wanted it to move vertically, the values would be `0 0 100` for example.)

Now we add the trigger. When the player touches the trigger, they will be promted with the hintstring with the door's cost, and when the player presses `F` (or whatever their Use button is) the door will be purchased. To create the trigger, right-click on the 2D grid and go to `trigger`|`use`, then move it in front of the door - remember to put it on the correct side of the door so the players can get to it! Bring up the Entity window with `N` and give it the following KVPs:
```
             targetname | zombie_door
            zombie_cost | VALUE
      script_noteworthy | magic_door
            script_flag | enter_zone_two
```
Replace `VALUE` with any of the following numbers: 100, 200, 250, 500, 750, 1000, 1250, 1500, 1750, 2000. These are the only valid values for doors/debris. You can make custom values but I won't get into that here. I'll set my new door to 1250.

I will explain the `script_flag`|`enter_zone_two` later, in [[YourMapName.gsc|todo]]. However, you do need to add a KVP to the already existing door's trigger - `script_flag`|`enter_zone_one`. 

Once those KVPs are entered, deselect everything, then select the trigger, then the door. It MUST be in that order. With both selected, press `W` on the keyboard - this will connect the trigger with the door. You should also see a new KVP appear on the trigger - `target`|`autoX` where X is whatever number it chooses, and a corresponding KVP on the door itself, `targetname`|`autoX`. You should also see a line pointing from the trigger to the door. For example, here's mine:

{F3297}

> Remember to save! Use Ctrl+S as a shortcut.

## Path nodes, lights, zones

Now we'll add `path nodes`. These are the big pink cubes scattered around your map. These allow the zombies to find a path to the players. Without the path nodes, or if the path nodes are too far apart, the zombies will stand still and confused, before eventually dying. I will just select a row of pathnodes and press `Space` to copy them, and move them to my new room, then repeat until the room is filled. Here's what my room looks like now:

{F3299}

Notice that I've put two path nodes directly in the doorway. You'll notice the already-existing door has this too. You might need to play around with the positioning of your path nodes to have them work properly.

Your room will need light. Either right-click the 2D grid and select `light`, or find an existing one and press `Space` to copy it.

{F3301}

You can play around with the colour, radius, and intensity of the light by bringing up the Entity window with `N`. I will leave the radius and intensity as they are, because increasing them too much will make the room blindingly bright. Feel free to play around with it though.

Now we add a zone. You may have noticed a brush surrounding the original room with the word `Volume` repeating on it. Press `N` and you will see the KVP `targetname`|`start_zone`. Don't worry about the `start_zone_spawners` for now, that will be covered in [Spawners](#spawners). The smaller pre-existing room doesn't yet have a zone, so I'll add one to it. Right-click on the 2D grid then go to `info`>`volume`, then extend it to cover the whole room. Give it the KVP `targetname`|`zone_one` or whatever you want to call the zone. I will then do the same for my new room, but I'll call that one `zone_two`.

I'll continue in Radiant for now but the zone is not yet finished - it needs declaring in script. See [YourMapName.gsc](todo).

## Barricades

First we make the gap for the barricade to be placed in. This works in a similar way to the gap for the door. To add a barricade for zombies to get through, right-click the 2D view and go to `misc`>`prefab`, which will open a folder called `_prefabs`. This contains a bunch of .map files which can be inserted into any other map file - if the prefab's .map file is edited, the prefabs in any map which includes it will be edited also. This is helpful for common items - like barricades! Select `factory_barricade.map` Align it with the hole you made in the wall. Here's my example (with `ActionNodes` filtered out for visibility):

{F3303}

Notice that the top of the `Traverse` brush aligns with the bottom of the hole. This means zombies, when playing the wall-hop traverse animation, will place their hands on the wall, rather than in the air or in the brush. I'm going to add a few more brushes to line the hole with a wooden window-frame, but you can do whatever.

## Spawners

You will probably have noticed the character models outside the building. These are spawners. Select one, copy it with `Space`, then move it next to the new barricade we just made.

One of the KVPs is `targetname`|`start_zone_spawners`, and there is a KVP for the starting zone, `target`|`start_zone_spawners`. This means any spawner with that targetname will spawn zombies that are linked to that zone. To link this spawner to our new zone, we must change the spawner's KVP to `targetname`|`zone_two_spawners` and add a KVP to zone two's `info_volume`, that is `target`|`zone_two_spawners`. Once you've done that, there should be a line connecting the spawner with the zone, like so: 

{F3305}

Don't forget to add pathnodes to the new barricade! Add some path nodes outside the building so zombies can walk to and from each barricade.

## Wall Weapons

To add a buyable weapon, right-click the 2D view, go to `misc`>`prefab` then navigate to the `_prefabs\zombiemode\` folder. Scroll down to the prefabs prefixed with `weapon_upgrade_` - these are wall weapon prefabs. I'll add the Thompson. Align it with the edge of the wall brush, like so: 

{F3307}

## Mystery Box

Find one of the other mystery boxes in the map. You'll see that it is all a bunch of separate models, with a clip and a trigger. Select all the models, and clip/trigger, then copy and move it. There will be a bunch of lines linking the copied box with the original, ignore these for now.

There are currently two mystery boxes in the map - boxes 0 and 1, so this one will be box 2. So you will need to rename many of the KVPs for this chest. Here is a list:
```
      TRIGGER:
          script_noteworthy | chest2
                     target | magic_box_lid_2
       
      BOX LID:
          targetname | magic_box_lid_2
              target | magic_box_weapon_spawn_2
       
      BOX BASE:
          targetname | magic_box_base_2
       
      RUBBLE (3 small crates plus teddy):
          script_noteworthy | chest2_rubble
       
      SCRIPT ORIGIN (red cube inside box):
          targetname | magic_box_weapon_spawn_2
              target | magic_box_base_2
```
To add another box, simply repeat this process but with `chest3` etc. Do not include more than 6 mystery boxes in any map. It's possible to add more but I won't go into that here.


Congratulations, you've now added a room to your map!
  


## Scripts

World at War uses `GSC` and `CSC` scripts (GSC is game scripts, CSC is client scripts). When you used the script placer, it will have placed some scripts in `root\mods\YourMapName`. You don't need to edit much to get your map working properly. Locate `root\mods\YourMapName\maps\` and you should find some scripts. For now, the only script I need to edit is `tutorialmap.gsc`, but for you it will be `YourMapName.gsc`.

Don't worry if you don't have the first clue about code, I'll explain the steps. Open the files in any text editor of your choice. Notepad will do, but I recommend [Sublime Text](https://www.sublimetext.com/) if you want to get into more advanced scripting in the future.

## YourMapName.gsc

Find this (should be around line 54):
``` php
      // Magic Boxes -- The Script_Noteworthy Value Names On Purchase Trigger In Radiant
          boxArray = [];
          boxArray[ boxArray.size ] = "start_chest";
          boxArray[ boxArray.size ] = "chest1";
          boxArray[ boxArray.size ] = "chest2";
          boxArray[ boxArray.size ] = "chest3";
          boxArray[ boxArray.size ] = "chest4";
          boxArray[ boxArray.size ] = "chest5";
          level.DLC3.PandoraBoxes = boxArray;
```
I only used `start_chest`, `chest1` and `chest2`, so I will comment out the other three. To comment out lines, use two forward slashes - `//`. Mine now looks like this:
``` php
      // Magic Boxes -- The Script_Noteworthy Value Names On Purchase Trigger In Radiant
          boxArray = [];
          boxArray[ boxArray.size ] = "start_chest";
          boxArray[ boxArray.size ] = "chest1";
          boxArray[ boxArray.size ] = "chest2";
          // boxArray[ boxArray.size ] = "chest3";
          // boxArray[ boxArray.size ] = "chest4";
          // boxArray[ boxArray.size ] = "chest5";
          level.DLC3.PandoraBoxes = boxArray;
```
Obviously you should only comment out any boxes you aren't using. I have also edited `level.start_score = 500;` to `50000` so I can buy doors when I test the map, without having to kill a bunch of zombies first. For you, this is optional.

Now find this (should be around line 127):
``` php
          add_adjacent_zone( "start_zone", "zone1", "enter_zone1" );
          add_adjacent_zone( "zone1", "zone2", "enter_zone2" );
```
These don't match the names of the zones in my map, so I'll change the first two parameters to the corresponding adjacent zones. The third parameter is the `script_flag` you set on the door triggers - see [Doors](#doors).
``` php
          add_adjacent_zone( "start_zone", "zone_one", "enter_zone_one" );
          add_adjacent_zone( "zone_one", "zone_two", "enter_zone_two" );
```
If you added any other zones, add another line and enter the zone names/flags accordingly.

That's all you need to edit in scripts for now.
  

## Compiling

> **NOTE**: I recommend using DidUknowiPwn's Launcher and Mod Tools, he has made a more informative GUI and has fixed a couple of issues with some tools. Download at [Mega.nz](https://mega.nz/#!N51xjLgI!ZhrvgwGOWnrodG12WlTZRYNiay-aQhOzmMejx9fC_ko) or [Mediafire](http://www.mediafire.com/download/6qq80ccxz6ugyan/CoD_WaW_Mod_Tools_-_Pwn_Edition_V1.1_June_2016.rar). I am using them, so the images used are of his launcher/tools.

## Compile FF

Open the Launcher window and navigate to the `Compile FF` tab. Select your map from the list. Tick the following boxes:

{F3309}
{F3311}

Click "Compile FF". If you get the error `EXE_ERR_HUNK_ALLOC_FAILED256`, close some memory-heavy programs and try again. DidUknowiPwn's tools fix this issue.

You should see the status bar say `Success` if it has compiled. If it has an error, look in the console and see if you can solve the issue.

{F3313}

Then I'll select `tutorialmap_patch`, tick `Build FastFile` then click `Compile FF`. This should only take a couple of seconds. If you get the error `EXE_COULDNT_LOADmaps/tutorialmap_patch.d3dbsp`, navigate to `root\zone_source\` and open `tutorialmap_patch.csv` in any text editor. Find this line and commment it out, like so:
```
      col_map_sp,maps/tutorialmap_patch.d3dbsp
```
becomes
```
      // col_map_sp,maps/tutorialmap_patch.d3dbsp
```
It should then compile fine. For the time being, don't worry about errors as long as the status bar says `Success`.

## Build Mod

Now navigate to the `Build Mod` tab. Select your mod from the drop-down list, then tick `Build mod.ff FastFile` and `Build IWD File`. In the box on the left, select everything except `mod.csv`. then click `Build Mod`.

## Test

You can either navigate to the `Run Game` tab, or just launch the game as you normally would. Either way, once the game is running, load the mod and start the game. Script Placer Z will have asked you to write a main menu solo button, but if you didn't do that, open the console with ` /`  then type `map tutorialmap` or whatever you called your map.

You should now be in-game!