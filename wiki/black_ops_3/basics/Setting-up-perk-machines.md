NOTE: **Juggernog, Quick Revive, Speed Cola, Double Tap, Stamin-up, Deadshot, Mulekick:** These machines are already included as prefabs in `<BlackOps3Root>/Usermaps/_prefabs/`. You can simply add them to radiant without any additional work

---

#Widows Wine==

First you need to download the already made prefab here: [download](https://mega.nz/#!1RAUQJIT!mPuMmkYN7zjAGBweBIroIedzt3WLoLtsq8EjOMuoicc)

Place the prefab in `BlackOps3Root/map_source/_prefabs/`.

Next open up your `mapname.gsc` in `usermaps/mapname/scripts/zm`.

Under the `//Perks` comment you'll see the base perk scripts, under the last line (Staminup) put:


lang=php
1. using scripts\zm\_zm_perk_widows_wine;


Close that file and open up `mapname.csc` in the same directory, find the `//Perks` line again and add the same code listed above to the script, save and close.

You can rebuild and use Widows Wine.

---

#Electric Cherry==

This machine requires some extra work, take your time to ensure it's done properly.

You need to rip the model with Wraith and import it to APE yourself.

Download for the already made prefab here: [download](https://mega.nz/#!Ud5DWBiZ!rqAOjEk1EJH7sr827jBZy3Ph6dkjzOD5FeaGU94VCM8)

Place the prefab in `BlackOps3Root/map_source/_prefabs/`.

Open up `BlackOps3Root/share/raw/scripts/zm/_zm_perk_electric_cherry.gsc`.

Find the `"//TODO update these to proper settings"` comment they left.

Modify all of those defines to say (Modify model name if you've changed it):


lang=cpp
1. define ELECTRIC_CHERRY_PERK_COST                   2000
2. define ELECTRIC_CHERRY_PERK_BOTTLE_WEAPON          "zombie_perk_bottle_cherry"
3. define ELECTRIC_CHERRY_SHADER                      "specialty_blue_electric_cherry_zombies"
4. define ELECTRIC_CHERRY_MACHINE_DISABLED_MODEL      "p6_zm_vending_electric_cherry_off" 
//                                                   ^^ Change this to your OFF xmodel
1. define ELECTRIC_CHERRY_MACHINE_ACTIVE_MODEL        "p6_zm_vending_electric_cherry_on" 
//                                                   ^^ Change this to your ON xmodel
1. define ELECTRIC_CHERRY_RADIANT_MACHINE_NAME        "vending_electriccherry"
2. define ELECTRIC_CHERRY_MACHINE_LIGHT_FX            "electric_cherry_light" 


Next find the function `enable_electric_cherry_perk_for_level()` and change it to:

lang=php
function enable_electric_cherry_perk_for_level()
{	
	// register ec perk for level
	zm_perks::register_perk_basic_info( PERK_ELECTRIC_CHERRY, "electric_cherry", ELECTRIC_CHERRY_PERK_COST, "Hold ^3[{+activate}]^7 for Electric Cherry [Cost: &&1]", GetWeapon( ELECTRIC_CHERRY_PERK_BOTTLE_WEAPON ) );
	zm_perks::register_perk_precache_func( PERK_ELECTRIC_CHERRY, &electric_cherry_precache );
	zm_perks::register_perk_clientfields( PERK_ELECTRIC_CHERRY, &electric_cherry_register_clientfield, &electric_cherry_set_clientfield );
	zm_perks::register_perk_machine( PERK_ELECTRIC_CHERRY, &electric_cherry_perk_machine_setup );
	zm_perks::register_perk_host_migration_params( PERK_ELECTRIC_CHERRY, ELECTRIC_CHERRY_RADIANT_MACHINE_NAME, ELECTRIC_CHERRY_MACHINE_LIGHT_FX );
	
	zm_perks::register_perk_threads( PERK_ELECTRIC_CHERRY, &electric_cherry_reload_attack , &electric_cherry_perk_lost  );
	
	if( IS_TRUE( level.custom_electric_cherry_perk_threads ) )
	{
		level thread [[ level.custom_electric_cherry_perk_threads ]]();
	}

	init_electric_cherry();
}


Next find the function `electric_cherry_perk_machine_setup()` and replace with:


lang=php
function electric_cherry_perk_machine_setup( use_trigger, perk_machine, bump_trigger, collision )
{
	use_trigger.script_sound = "mus_perks_ec_jingle";
	use_trigger.script_string = "electriccherry_perk";
	use_trigger.script_label = "mus_perks_ec_sting";
	use_trigger.target = "vending_electriccherry";
	perk_machine.script_string = "electriccherry_perk";
	perk_machine.targetname = "vending_electriccherry";
	if( IsDefined( bump_trigger ) )
	{
		bump_trigger.script_string = "electriccherry_perk";
	}
}


Finally, find and replace `vending_marathon` with `vending_electriccherry`.

Also find and replace `marathon_perk` with `electriccherry_perk`.

Save and close the file.

Next open up your `mapname.gsc` in `usermaps/mapname/scripts/zm`.

Under the `//Perks` comment you'll see the base perk scripts, under the last line (Staminup) put:


lang=cpp
1. using scripts\zm\_zm_perk_electric_cherry;


Close that file and open up `mapname.csc` in the same directory, find the `//Perks` line again and add the same code listed above to the script, save and close.

Next, include these scripts in your `mapname.zone` located at `BlackOps3Root/usermaps/mapname/zone_source`.

Add the following lines and modify the model name if you've changed it:


lang=php
//EC
xmodel,p6_zm_vending_electric_cherry_off
xmodel,p6_zm_vending_electric_cherry_on
scriptparsetree,scripts/zm/_zm_perk_electric_cherry.gsc
scriptparsetree,scripts/zm/_zm_perk_electric_cherry.csc


---

#More perks to come!==
- PhD Flopper
- Who's Who
- Vulture Aid
- Tombstone

---

//**Contributors**//
DTZxPorter
Harry Bo21
Exofile