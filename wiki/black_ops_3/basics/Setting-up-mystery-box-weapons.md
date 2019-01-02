With everything you do script wise, it is //always// a good idea to backup your scripts.

Take your time - you only have to to the first part once, after that for new mods and maps it's very simple and adaptable`!

First, go to `BlackOps3Root/share/raw/gamedata/weapons/zm/` and make a copy of `zm_levelcommon_weapons.csv`, name it something like `zm_test_weapons.csv`.

NOTE: This will be your map / mod specific weapons list. You may add or remove lines in this file to include them. The first two columns are `normal weapon file`, `upgraded weapon file`, and the 10th column is whether it's included in the box or not.

After you're done, save and close this file. 

Next open up `zm_usermap.gsc` in `BlackOps3Root/share/raw/scripts/zm`.

Find all references to :

lang=php
load_weapon_spec_from_table("gamedata/weapons/zm/zm_levelcommon_weapons.csv", 1);


Change the csv name to the name you gave the csv earlier :

lang=php
load_weapon_spec_from_table("gamedata/weapons/zm/zm_test_weapons.csv", 1);


Repeat this step in `zm_usermap.csc`, `YOUR_MAP_NAME.csc` and `YOUR_MAP_NAME.gsc`.

You've now made it easier to modify weapons for multiple mods!

Last step, open up your `mapname.zone` file, add the following entries to it:


lang=php
//Custom box weapons
stringtable,gamedata/weapons/zm/zm_test_weapons.csv // Whatever name you gave your csv and referenced in the 4 scripts
//Custom usermap modifications
scriptparsetree,scripts/zm/zm_usermap.gsc // Only if you do not already have this in this file elsewhere
scriptparsetree,scripts/zm/zm_usermap.csc // Only if you do not already have this in this file elsewhere


Your new `weapons.csv` should appear in game now.

(NOTE) From now on, you just have to make a copy of the `weapons.csv`, going this route keeps things clean and easy. To have a different set of weapons of a different map, simply have another csv with another name and change the references to it again in those 4 scripts ( `zm_usermap.gsc`, `zm_usermap.csc`, `YOUR_MAP_NAME.csc` and `YOUR_MAP_NAME.gsc` ) we changed in the tutorial.

--- 

//**Contributors**//
DTZxPorter
Harry Bo21
