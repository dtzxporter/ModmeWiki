# Setting Up Traps

{F42024}

*INCLUDES:*

- Electric Trap
- Fire Trap
- Turret Trap
- Flogger Trap
- Centrifuge Trap
- Flinger Trap
- Chain Trap
- Acid Trap
- Fan Trap
- Gate Trap

A set of 10 different prefabs are set up in the download ( if you need more, copy paste the trap "H" prefab of the type you want, open it in a text editor, and search and replace "trap_a" with "trap_whatever" )

Download: [Everything You Need](https://mega.nz/#!lQsAiJiC!-FHaYCLXKc9iZfQbzI-XjHYx14ahaESwFqxlhmRvlNA)

*Instructions*

- Download the files and extract them into your root directory ( Root directory is your Black Ops 3 install )

*Scripting:*

- Open your `mapname.gsc`
- Find this line:

```
#using scripts\zm\_zm_perk_staminup;
```

add this underneath:
```
// Traps
#using scripts\zm\_zm_trap_electric;
#using scripts\zm\_zm_trap_fire;
#using scripts\zm\_hb21_sym_zm_trap_turret;
#using scripts\zm\_hb21_zm_trap_flogger;
#using scripts\zm\_hb21_zm_trap_centrifuge;
#using scripts\zm\_hb21_zm_trap_flinger;
#using scripts\zm\_hb21_sym_zm_trap_chain;
#using scripts\zm\_hb21_sym_zm_trap_fan;
#using scripts\zm\_hb21_sym_zm_trap_acid;
#using scripts\zm\_hb21_sym_zm_trap_gate;
```

- Open `mapname.csc`
- Find this line:

```
#using scripts\zm\_zm_perk_staminup;
```

add this underneath:

```
// Traps
#using scripts\zm\_zm_trap_electric;
#using scripts\zm\_zm_trap_fire;
#using scripts\zm\_hb21_zm_trap_centrifuge;
#using scripts\zm\_hb21_sym_zm_trap_fan;
#using scripts\zm\_hb21_sym_zm_trap_acid;
```

*Zone:*

- Open your `mapname.zone` ( you can right click your map in launcher and click `Open Zone File` )
- At the bottom paste this:

```
include,hb21_traps
```

*Setting up the Sounds:*

- Go to `root/usermaps/YOUR_MAP/sound/zoneconfig/`
- You will find a SZC file with your maps name. Open this in any text editor

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

Add this under it, its pretty much copy paste with the name and filename changed

``` json
{
"Type" : "ALIAS",
"Name" : "trap_sounds",
"Filename" : "trap_sounds.csv",
"Specs" : [ ] 
},
```

*Radiant:*

- Open your map in radiant
- Place whichever traps you want to use
- The prefabs are located at - `map_source/_prefabs/zm/harrybo21_prefabs/traps`

> **IMPORTANT:** If you place for example a `electric trap A` you must not "also" place a `fire trap A` - only one of each may exist

> **NOTE:** If you need more than 10 traps, you can create more by `modifying the KVPs` on further traps

*You are DONE*

Ok, so assuming you've followed these steps exactly - you now just need to recompile your map and link in launcher. Now go test!

*Additional KVPs*

If you want to change a traps price, select the prefab and add this KVP ( change the cost to whatever you like )

```
zombie_cost - 5000
```

If you want to make sure a trap cannot be used until a door is opened, select the prefab and add this KVP ( replace with the script_flag from your door trigger )

```
script_flag_wait - activate_zone_1
```

If you are using local power switches, select the prefab and add this KVP ( change to the appropriate power zone number )

```
script_int - 0
```

_Contributors:_
- DTZxPorter
- ZeRoY
- SethNorris
- Symbo
- Harry Bo21