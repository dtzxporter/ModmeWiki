# Setting Up The Apothicon Servant

Download: [Everything You Need](https://mega.nz/#!AJkhAaLL!WhODS8g5YGgae3jFYSn5TsZy0vV7kQlClalWbkBew94)

*Instructions*

- Download the files and extract them into your root directory ( Root directory is your Black Ops 3 install )

*Scripting:*

- Open your `mapname.gsc` and `mapname.csc`
- In each find this line:
```
#using scripts\zm\_zm_perk_staminup;
```
In both files, underneath add the following:
```
// APOTHICON SERVANT
#using scripts\zm\_zm_weap_idgun;
```

- Next in `mapname.gsc`
- Find this line:

``` php
usermaps::main();
```

Under it add this:

``` php
level.b_allow_idgun_pap = 1;
level.idgun_weapons = [];
level.idgun_weapons[ 0 ] = getWeapon( "idgun_0" );
level.idgun_weapons[ 1 ] = getWeapon( "idgun_1" );
level.idgun_weapons[ 2 ] = getWeapon( "idgun_2" );
level.idgun_weapons[ 3 ] = getWeapon( "idgun_3" );
level.idgun_weapons[ 4 ] = getWeapon( "idgun_upgraded_0" );
level.idgun_weapons[ 5 ] = getWeapon( "idgun_upgraded_1" );
level.idgun_weapons[ 6 ] = getWeapon( "idgun_upgraded_2" );
level.idgun_weapons[ 7 ] = getWeapon( "idgun_upgraded_3" );
```

*Adding the weapon to the Mystery Box and Pack a Punch:*

- Go to `root/share/raw/gamedata/weapons/zm/` and open `zm_levelcommon_weapons.csv`
- Add this to the bottom:

```
idgun_0,idgun_upgraded_0,,10000,wpck_ray,,,,,TRUE,FALSE,FALSE,,,FALSE,FALSE,special,TRUE,,
idgun_1,idgun_upgraded_1,,10000,wpck_ray,,,,,TRUE,FALSE,FALSE,,,FALSE,FALSE,special,TRUE,,
idgun_2,idgun_upgraded_2,,10000,wpck_ray,,,,,TRUE,FALSE,FALSE,,,FALSE,FALSE,special,TRUE,,
idgun_3,idgun_upgraded_3,,10000,wpck_ray,,,,,TRUE,FALSE,FALSE,,,FALSE,FALSE,special,TRUE,,
```

Next open your maps `Zone file`, and add this line if you dont have it already:

```
stringtable,gamedata/weapons/zm/zm_levelcommon_weapons.csv
```

*You are DONE*

Ok, so assuming you've followed these steps exactly - you now just need to link your map in launcher. Now go test!

_Contributors:_
- Harry Bo21
- DTZxPorter