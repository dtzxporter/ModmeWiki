# Porting weapons from Apex Legends to Black Ops 3

### Introduction & Prerequisites
Porting a weapon from Apex Legends to Black Ops 3 is a bit more complicated then porting weapons from older CoD games. This tutorial will cover everything on the Maya side only. If you are struggling setting everything up in APE first it is suggested that you port weapons from old games first until you understand APE better. Any problems feel free to message me on discord at: Thomas Cat#7648 or on [Twitter](https://twitter.com/SpSSdyMain).

- **Required programs: [Autodesk Maya](http://www.autodesk.com/products/maya/overview), [Conversion Rig](https://modme.co/index.php?view=topic&tid=2860), [Black Ops 3](http://store.steampowered.com/app/311210/), [Black Ops 3 Mod Tools](http://steamcommunity.com/app/455130), [Legion](https://wiki.modme.co/wiki/apps/Legion.html), [CodMayaTools](https://github.com/LunaRyuko/CoDMayaTools/releases), [SeTools](https://github.com/dtzxporter/SETools)**

The basic workflow of obtaining and converting the Apex Legends assets:
 - Dump the games assets
 - Collect the required assets
 - Fix and Export the View Model
 - Create and Export a World Model
 - Setting up the Conversion Rig
 - Convert and Fix ADS Animations
 - Convert Normal Animations
 - Create and Convert Missing/Broken Animations

## Dumping the games assets
It is paramount that you read the instructions given to you on the Legion Wiki page before you attempt to rip assets. This will give you a understanding of the tool so you do not make any mistakes.

Go to where Apex Legends has been installed on your computer and navigate to `paks\Win64\`

Type `cmd` in the address bar at the top of the file explorer window in the Apex Legends directory.

Type this command: `--exportmdl --imgfmt=tiff` and drag in `common.rpak`.

Hit enter and wait for this process to finish.

When it has finished type `--exportanim` and drag in `common.rpak`.

Hit enter and wait for this process to finish.

> **NOTE:** The game shouldn't be open while doing this process and you shouldn't need to export any other rpak file as `common.rpak` is where the weapons are stored.

## Collecting the required assets
You should find the exported files under a folder called `exported_files`. I suggest creating a seperate folder for the weapon you want to port with subfolders for the models, anims, xanimbins, xmodelbins.

Go into the export folder for Legion and go into the `models` folder. Locate the weapon you want to port, usually has a `atpov` prefix, and store it somewhere safe.

Go back into the Legion export folder and go into the `animations` folder. Get the folder with the same name as the models you stored and store the animations somewhere safe, preferably in the same folder as the models.

## Fixing and Exporting the View Model

Open a Maya window and drag in the SeModel file for your weapon.

Navigate to the `Apex_Shortcuts` Shelf.

Click `Model`. You will notice the weapon has now moved, scaled up and extra joints have been deleted.

Create a new Joint and move it to the muzzle of the weapon. Parent this joint under `def_c_base` and rename the joint to `tag_flash`. This is where the muzzle flash FX is going to be played.

Save this as a .MA in a safe space. This will be used for animations. Anything from this point on **DO NOT SAVE**

Delete the mesh of the attachments you do not wish to include in your weapon and, optionally, delete the joint it was binded to.

Rename `def_c_base` to `tag_weapon`.

Export this as the View Model.

> **NOTE:** If you do not want to redo the steps below "DO NOT SAVE" then keep the Maya window open while working on the World Model.

## Creating and Exporting the World Model.

Select all of the meshes and, making sure your on the `Rigging` tab, click `Skin - Unbind Skin`.

Select all of the Joints **EXCEPT TAG_WEAPON** and all of the Meshes.

Move the weapon so that the weapon is orientated correctly and the grip is in the centre with the trigger just above the grid.

Select `tag_weapon` + all of the meshes and, making sure your still on the `Rigging` tab, click the box next to `Skin - Bind Skin`. Make sure the settings are the same as the ones in [this](https://i.imgur.com/jdJ4Y2N.png) screenshot and then hit `Apply`

The world model is now completed and you can now export it and save the scene.

> **NOTE:** If you want your world model to be perfect you can export a BO3 world model and use that to get the world model as close as possible. 

## Setting up the Conversion Rig

Open up the Apex Legends to Black Ops 3 Conversion Rig in Maya and drag the Viewmodel you saved onto it.

Making sure your still on the `Apex_Shortcuts` Shelf, click `Attach`.

The Conversion Rig is now setup for converting animations, you should now save the scene.

> **NOTE:** IF you prefer to get a First Person view you can click the `FPS` button on the `Apex_Shortcuts` shelf to go into a FPS Perspective to preview what the weapon should look like ingame. If you want to get out of this view just double click the `FPS` button.

## Converting and Fixing the ADS Animation

Drag in the `ads_in_0` animation.

Click `Bake` in the `Apex_Shortcuts` Shelf.

Click `ADS` in the `Apex_Shortcuts` Shelf.

Export the animation as `ads_up`.

Tick the box `Export Animation Reversed` in the CodMayaTools window and then export the animation as `ads_down`.

> **NOTE:** To speed things up there is a button on the `Apex_Shortcuts` shelf that says `Tools` which will take you straight to the Anim Export window.

## Convert Normal Animations



