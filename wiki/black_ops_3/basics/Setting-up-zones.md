# Setting Up Zones

*Setting up in Radiant*

You will have something like this example, which has 2 zones:

{F62}

You need to select a `info_volume` from the entity browser:

{F64}

Cover your zone, but keep to the walls - you do not want these intersecting with other zones. If you cannot cover your entire zone, don't worry for now. After you've set the KVPs on the volume, you can copy and paste it as many times as needed to cover your entire zone.

{F66}

You'll need to give the `info_volume` some KVPs now. `targetname` can be anything unique. For your first zone, choose `start_zone` as that's already set up in the mod tools.

Also give it a new KVP - `target` with the value being the `targetname` of your spawners for this zone. Either that, or select the zone, then the spawners, and press W (in that order).

It will also need the KVP `script_noteworthy - player_volume`.

{F68}

If you were not able to cover your zone fully, you may now copy and paste the volume and shape it so you can.

Repeat the process to create another zone, but also copy and paste a zombie spawn point, and change its KVPs to create spawners for the new zone.

{F70}

Make sure the new zone is targeting these new spawners.

{F72}

*Setting up in script*

Open your `mapname gsc` and find this:

``` php
function usermap_test_zone_init()
{
	level flag::init( "always_on" );
	level flag::set( "always_on" );
}	
```

Remove the two flag lines.

Now you need to add your zones using the following command:

``` php
zm_zonemgr::add_adjacent_zone( "ZONE TARGETNAME",		"OTHER ZONE TARGETNAME",		"SCRIPT FLAG TO ACTIVATE ZONE" );
```

So, for our example, it would appear as this:

``` php
function usermap_test_zone_init()
{
	zm_zonemgr::add_adjacent_zone( "start_zone",		"zone_1",		"open_zone_1" );
}
```

First zone is the zone player is in.
Second zone is the zone to be activated
Script flag is any string, that you will use later on your door blocker to activate the zone.

*Finally*

This is all you need to do to set up the zones, however we haven't covered actually activating it. We would use a door to enter it and thus activate it. Doors are covered [here]({{ ''/wiki/black_ops_3/basics/Setting-up-doors.html' | relative_link }})

> **NOTE:** Although we have created a second zone, I believe because it's inactive you will still die by entering it.

---

_Contributors:_
- Harry Bo21
- DTZxPorter