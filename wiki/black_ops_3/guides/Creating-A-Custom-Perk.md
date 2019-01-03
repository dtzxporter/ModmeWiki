# Creating A Custom Perk

Download: [Everything you need](https://mega.nz/#!sEUjTSCJ!u9PZo6Pjx4-mzsblOSg6R5Ukqrac2_XfI2vAlSd0LBE)

*Instructions*

- Download the files and extract them into your root directory ( Root directory is your Black Ops 3 install )

*Step 1 : Setting the scripts up*

- Add the GSC, CSC and GSH to `root/usermaps/YOUR_MAP_NAME/scripts/zm/`
- Open the GSH, GSC and CSC and find / replace all references as follows:

``` php
CUSTOM_PERK

YOUR_PERK_NAME // eg VULTUREAID

custom_perk

your_perk_name // eg vultureaid
```

- Open your mapname GSC and CSC from `root/usermaps/YOUR_MAP_NAME/scripts/zm/` and add 

```
#using scripts\zm\_zm_perk_custom_perk;
```

*Step 2 : Add to your zone*

- Right click your map in launcher and click !!Edit Zone File!!
- Add the following:

```
scriptparsetree,scripts\zm\_zm_perk_custom_perk.gsc
scriptparsetree,scripts\zm\_zm_perk_custom_perk.csc
scriptparsetree,scripts\zm\_zm_perk_custom_perk.gsh
```

*Step 3 : Radiant*

- Place the perk prefab in your map `map_source/_prefabs/zm/harrybo21_prefabs/perks/vending_custom_perk_struct.map`

*Step 4 : Sounds*

- Go to `root/raw/sound/aliases/` and open `custom_perk_sounds.csv`
- Change the jingle and sting alias to your desired sounds and change the references to "custom_perk"
- Go to `root/usermaps/YOUR_MAP_NAME/sound/zoneconfig` Open `YOUR_MAP_NAME.szc` and add a new alias:

``` json
{
	"Type" : "ALIAS",
	"Name" : "custom_perk_sounds",
	"Filename" : "custom_perk_sounds.csv",
	"Specs" : [ ] 
},
```

*Step 5 : Compile and Test*

- In Launcher, tick `Compile and link` then click `Build` - this should be enough to create your machine and be able to buy it

> **NOTE:** THIS IS SET UP FOR PORTERS LUA MOD, FOLLOW HIS TUTORIAL ON SETTING UP THE ICON FOR THE PERK, THIS TUTORIAL HAS SET UP EVERYTHING ON THE GSC AND CSC SIDE.

- You will also need to set your models, shaders, bottle weapon files etc in the perk GSH - and if you change the specialty you use, make sure to change the KVP on the prefab - and the reference in the GSH
- When you add your models and shaders to the gsh properly, you will also need to add them to your zone:

```
xmodel,MODEL_NAME
weapon,BOTTLE_WEAPON_FILE_NAME
```

- You can copy paste this template as many times as you like to create more perks, although they must use unique specialties, from the list ive provided in the download, and youll need to change the script names ( and references to them )

_Contributors:_
- Harry Bo21
- DTZxPorter