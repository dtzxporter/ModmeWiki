# Porting weapons from Apex Legends to Black Ops 3

### Introduction & Prerequisites
Porting a weapon from Apex Legends to Black Ops 3 is a bit more complicated then porting weapons from older CoD games. This tutorial will cover everything on the Maya side only. If you are struggling setting everything up in APE first it is suggested that you port weapons from old games first until you understand APE better. Any problems feel free to message me on discord at: Thomas Cat#7648
- **Required programs: [Autodesk Maya](http://www.autodesk.com/products/maya/overview), [Conversion Rig](https://modme.co/index.php?view=topic&tid=2860), [Black Ops 3](http://store.steampowered.com/app/311210/), [Black Ops 3 Mod Tools](http://steamcommunity.com/app/455130), [Legion](https://wiki.modme.co/wiki/apps/Legion.html), [CodMayaTools](https://github.com/LunaRyuko/CoDMayaTools/releases), [SeTools](https://github.com/dtzxporter/SETools)**

The basic workflow of obtaining and converting the Apex Legends assets:
 - Dump the games assets
 - Collect the required assets
 - Fix and Export the View Model
 - Create and Export a World Model
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

Open a Maya window and 
