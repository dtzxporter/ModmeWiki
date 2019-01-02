  *Setting up in Radiant**

Download the prefabs and extract to root/map_source ([PREFABS](https://mega.nz/#!8dMykIJC!gmNnRB4_y8VdVBu7fxamGjIp5WoSDW8vvrtVjsCa8zk)).

Place the new power switch prefab (delete any old one you might have).

Select your sun_volume. You'll see there are 4 sets of light state KVPs. You probably only have one set up. Set at least the first 2 up (//use the same SSI if you don't want the game lighting to change//).

{F60}

  *Setting up in script**

Open your mapname gsc and find the function `zm_usermap::main();`

Inside it put it put this:

lang=php
//Power Lights
thread power_lights();

At the end of your script add this :

lang=php
function power_lights()
{
	level flag::wait_till( "power_on" );
	level util::set_lighting_state( 0 );
	level flag::wait_till( "power_off" );
	level util::set_lighting_state( 1 );
	power_lights();
}


Then recompile and test your map.

---

//**Contributors**//
Harry Bo21
DTZxPorter