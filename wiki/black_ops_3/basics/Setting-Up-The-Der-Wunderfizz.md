# Setting Up Der Wunderfizz

Download: [Everything You Need](https://mega.nz/#!sMsRWDQB!ggB948vS95WXpru3oa_gnr199Y9O5OPzg_pCGjxoqAg)

*Instructions*

- Download the files and extract them into your root directory ( Root directory is your Black Ops 3 install )

*Radiant:*

Place as many of the `vending_random_perk_spawnable` prefab as you would like

That is all for radiant

*Scripting:*

- Open your `mapname.gsc` and `mapname.csc`
- In each find this line:
```
#using scripts\zm\_zm_perk_staminup;
```
In both files, underneath add the following:
```
// DER WUNDERFIZZ
1. using scripts\zm\_zm_perk_random;
```

- Next in `mapname.gsc`
- Find this line:

``` php
usermaps::main();
```

Under it add this for each perk you want to be in the fizz, add this line, and use your perk specialty:

``` php
zm_perk_random::include_perk_in_random_rotation( "perk_specialty" );
```

Heres a example for the 13 official perks:

``` php
zm_perk_random::include_perk_in_random_rotation( "specialty_quickrevive" );
zm_perk_random::include_perk_in_random_rotation( "specialty_armorvest" );
zm_perk_random::include_perk_in_random_rotation( "specialty_doubletap2" );
zm_perk_random::include_perk_in_random_rotation( "specialty_fastreload" );
zm_perk_random::include_perk_in_random_rotation( "specialty_deadshot" );
zm_perk_random::include_perk_in_random_rotation( "specialty_phdflopper" );
zm_perk_random::include_perk_in_random_rotation( "specialty_staminup" );
zm_perk_random::include_perk_in_random_rotation( "specialty_additionalprimaryweapon" );
zm_perk_random::include_perk_in_random_rotation( "specialty_tombstone" );
zm_perk_random::include_perk_in_random_rotation( "specialty_whoswho" );
zm_perk_random::include_perk_in_random_rotation( "specialty_electriccherry" );
zm_perk_random::include_perk_in_random_rotation( "specialty_vultureaid" );
zm_perk_random::include_perk_in_random_rotation( "specialty_widowswine" );
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
add this under it, its pretty much copy paste with the name and filename changed
``` json
{
"Type" : "ALIAS",
"Name" : "wunderfizz_sounds",
"Filename" : "wunderfizz_sounds.csv",
"Specs" : [ ] 
},
```

*Zone:*

- Open your `mapname.zone` ( you can right click your map in launcher and click `Open Zone File` )
- At the bottom paste this:

``` php
// DER WUNDERFIZZ
scriptparsetree,scripts/zm/_zm_perk_random.gsh
scriptparsetree,scripts/zm/_zm_perk_random.gsc
scriptparsetree,scripts/zm/_zm_perk_random.csc
fx,harry/wonderfizz/fx_wonderfizz_sparks.efx
fx,harry/wonderfizz/fx_wonderfizz_bottle_glow.efx
```

*You are DONE*

Ok, so assuming you've followed these steps exactly - you now just need to recompile your map and link in launcher. Now go test!

_Contributors:_
- Harry Bo21
- DTZxPorter