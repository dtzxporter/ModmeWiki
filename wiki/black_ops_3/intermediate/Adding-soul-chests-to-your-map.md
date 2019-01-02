{F2526}

Download :

[[Everything You Need|https://mega.nz/#!IRs3EIKD!plDhrAb-acdQRVnLr-1zNiVj8oDPF7GzHwD-qyIOP8g]]

  *Setting up in Radiant**

Download the prefabs and other files and extract !!all except for the "USERMAPS - OPEN ME" folder and .zone file!! to your root directory ( Root directory is your Black Ops 3 install )

Now open your map in Radiant

Place your first soul chest, by creating a !!misc_prefab!! - the prefab you want to place is located at !!_prefabs/zm/harrybo21_prefabs/soul_chests/soul_chest.map!!

You will not be able to see the radius it will work, unless you stamp the prefab. To do so, make sure the !!prefab is selected and right click -> Prefab -> Stamp Prefab!!

{F2501}      {F2505}

Any Zombies killed by a player within this radius, will be 'fed' ( for lack of a better term ) to this soul chest

To adjust this radius, select the !!Orange Cube!! - Press 'N' on your keyboard, and edit the 'Radius' and 'Angles' KVPs

{F2507}

If you cant get to the Orange Cube because something is in your way, Select that something - and !!press 'H' to hide it!!. To unhide hidden objects, simply !!hold 'shift' and press 'H'!! again

Now, in the example, you can see that the radius of my chest goes through a wall. We don't want Zombies on the other side of this wall to 'feed' the chest, so to prevent that

Create a !!trigger_multiple!!

cover the area you want to 'exclude' with the trigger

{F2509}

now open its KVPs by having it selected and pressing 'N' on your keyboard

In the !!targetname!! kvp, give it this value

!!harrybo21_chest_ignore_area!!

{F2511}

This part of the soul chests radius will now be 'ignored' - you will want to do this to stop chests getting activated in other areas

You can copy paste this trigger as required

For multiple chests, you need only repeat these steps as required. Place the prefab, stamp it ( not 'required' per se, but you cant edit its radius without effecting 'all' unstamped prefabs, and will not be able to 'see' the radius in Radiant ) and place 'excluder' triggers as required

One final thing to do in Radiant now

As a reward, I have set the chests up for now to spawn a Ragnarok DG-4 at your desired location. Similar to the Annihilator with the 'Fly Trap' Easter Egg in 'The Giant'

To define !!where the DG-4 will spawn!! when all the chests are completed, place a !!script_struct!! - give this one the !!targetname!! - !!dg4_spawn!!

{F2513}

This completes everything you need to do in Radiant. Remember, !!place as many chest prefabs as you want!!, and !!copy paste the excluder trigger as you require!!

  *Setting up in Script**

First, go to your map folder, you will find this in !!root/usermaps/YOUR_MAP/!!

In the download, open the 'usermaps - OPEN ME' folder, and open the 'YOUR_MAP' folder

Drag the two folders into your map folder

{F2515}

Now open the !!scripts!! folder and open the !!zm!! folder

In here you will find a GSC and a CSC named the same as your map. Open the !!GSC!!

Under one of the other !!#using!! lines near the top of the script, add the following



1. using scripts\zm\_zm_soul_chests;


{F2517}

This is all that is 'required' for the script side of this tutorial, however there are some !!settings!! you may want to edit, or you may want to !!change the rewards!! for either completing !!one!! chest or !!all!! chests

If you open the !!_zm_soul_chests.gsh!! you will see the bottom section is some settings you can change as you see fit

{F2519}

To change any setting, you only need to change the number beside it

!!SOULCHEST_START_AMOUNT!! This is the amount of kills required to complete the first chest
!!SOULCHEST_START_ADD_AMOUNT!! This is the amount 'added' to the current amount each time a chest is completed increasing the requirement on the following chests
                                                                                                      If you want the same amount required on each chest, set this to 0
!!SOULCHEST_TIMEOUT!! This is how long a chest will wait before closing and resetting its current collected 'souls' counter. Like in Origins, if there was a large delay between you killing zombies near the chest, it would close and reset
                                                                  Just set some ludicrously high number if you want to stop it timing out, i havent bothered to make a way to disable it yet

Also, if you have some basic understanding of scripting,  you can easily change the rewards, open the !!_zm_soul_chests.gsc!!

You'll see these two sections

{F2521}

The !!top function!!, is what will happen each time a chest is completed, i set it up to give all players 500 points, and spawn a random powerup for now ( !!This function will not occur on the last chest!! )

The !!bottom function!! is what will happen when 'all chests' are completed, I set it to give all players 1000 points, spawn a power up and spawn the Ragnarok DG-4

Changing these rewards, if you understand a little scripting, is fairly easy to do. Just remember the variable 'origin' is the location of the chest that was completed

  *Setting up the Sounds**

There is currently only 2 sounds anyway, a open and a close sound. None the less, to set these up, go to !!root/usermaps/YOUR_MAP/sound/zoneconfig/!!

You will find a SZC file with your maps name. Open this in any text editor

Find this section ( Be aware that the copy of the SZC  we are originally given is horribly formatted )



"Sources" : [
{
	"Type" : "ALIAS",
	"Name" : "user_aliases",
	"Filename" : "user_aliases.csv",
	"Specs" : [ ] 
},


add this under it, its pretty much copy paste with the name and filename changed

{
	"Type" : "ALIAS",
	"Name" : "soul_chests",
	"Filename" : "soul_chests.csv",
	"Specs" : [ ] 
},

{F2523}

Assuming you have done this correctly, the sounds will now be working after you next 'link' the map

  *Adding the assets to your Zone File**

To open your zone file, either navigate to it !!root/usermaps/YOUR_MAP/zone_source/YOUR_MAP.zone!! - or just right click your map in launcher, and select !!Edit Zone File!!

At the bottom of the file, add the following



// SOUL CHESTS
fx,harry/soul_chest/fx_soul_chest_blue_fire
fx,harry/tomahawk/fx_tomahawk_trail
scriptparsetree,scripts/zm/_zm_soul_chests.gsc
scriptparsetree,scripts/zm/_zm_soul_chests.gsh
xanim,o_zombie_dlc4_challenge_box_open
xanim,o_zombie_dlc4_challenge_box_close
rawfile,animtrees/soul_box.atr


  *You are DONE**

Ok, so assuming you've followed these steps !!exactly!! - you now just need to recompile your map and link in launcher. Now go test your super awesome Soul Chests!

  *Contributors**
Harry Bo21
DTZxPorter
Redspace200