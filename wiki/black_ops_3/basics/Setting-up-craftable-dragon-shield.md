# Setting Up Craftable Dragon Shield

Download: [Everything You Need](https://mega.nz/#!xFMEyS7J!H0bizKNtmIU4IKtRI-xd8o08hfq5F30oUb4fZAdYoQE)

*Instructions*

- Download the files and extract them into your root directory ( Root directory is your Black Ops 3 install )

*Radiant:*

You will find the prefab for the craftable table at:

``map_source/_prefabs/zm/harrybo21_prefabs/dragon_shield/dragonshield_craftable_bench.map``

You will find 3 more prefabs for the individual parts of the shield:

```
map_source/_prefabs/zm/harrybo21_prefabs/dragon_shield/dragonshield_head.map
map_source/_prefabs/zm/harrybo21_prefabs/dragon_shield/dragonshield_pelvis.map
map_source/_prefabs/zm/harrybo21_prefabs/dragon_shield/dragonshield_window.map
```

Place all of these in radiant. If you want multiple locations for parts, place multiple of that prefab

You will also find this prefab:

`map_source/_prefabs/zm/harrybo21_prefabs/dragon_shield/dragonshield_upgrade_trigger.map`

A trigger will spawn here for players to upgrade the shield to "Tiamat's Maw" just as in Gorod Krovi. Place one or more of this if you wish to use this feature

That is all for radiant

*Scripting:*

Open your mapname.gsc and csc

In each find this line:

`using scripts\zm\_zm_perk_staminup;`

In both files, underneath add the following:
``` php
// DRAGON SHIELD
using scripts\zm\_zm_weap_dragonshield;
using scripts\zm\craftables\_zm_craft_dragonshield;
```

*Setting up the Sounds:*

There is currently only 2 sounds anyway, a open and a close sound. None the less, to set these up, go to `root/usermaps/YOUR_MAP/sound/zoneconfig/`

You will find a SZC file with your maps name. Open this in any text editor

Find this section ( Be aware that the copy of the SZC we are originally given is horribly formatted )
``` json
"Sources" : [
{
	"Type" : "ALIAS",
	"Name" : "user_aliases",
	"Filename" : "user_aliases.csv",
	"Specs" : [ ] 
},
```

add this under it, its pretty much copy paste with the name and filename changed
``` json
{
"Type" : "ALIAS",
"Name" : "dragon_shield_sounds",
"Filename" : "dragon_shield_sounds.csv",
"Specs" : [ ] 
},
```

*Zone:*

Open your maps "Zone" file and add the following :
```
include,harrybo21_dragon_shield
```

*You are DONE*

Ok, so assuming you've followed these steps exactly - you now just need to recompile your map and link in launcher. Now go test your super awesome Dragon Shield!

_Contributors:_
- Harry Bo21
- DTZxPorter
- EasySkanka
- Redspace200
- Zeroy