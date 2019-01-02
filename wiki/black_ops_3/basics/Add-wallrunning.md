# Add Wallrunning

 _Setting up the area in radiant:_

- First, map a wall where you want the player to run on. It must be a solid surface.
- Next, place another brush on the strip you want the player to run on. This brush must be a `trigger_multiple`. _Note: your brush must be thick enough to hold the player to properly register._
- Next set the `targetname` KVP on the brush to `wallrun_trigger`
- Next, open your mapname.gsc in `usermaps/mapname/scripts/zm`
- In the main function add the following:


``` php
// Wallrunning
SetDvar( "wallrun_enabled", 1 );
// Enable segments
level thread setup_wallrun();
```

Then add these three functions outside your main:

``` php
function setup_wallrun()
{
	players = GetPlayers();
	foreach(player in players)
	{
		player AllowWallRun(false);
		player.iswallrunning = false;
	}

	wallrun_trigger = GetEntArray("wallrun_trigger", "targetname");
	foreach(trig in wallrun_trigger)
	{
		trig thread wallrun_logic();
	}
}

function wallrun_logic()
{
	while(1)
	{
		self waittill("trigger", player);
		if(!player.iswallrunning)
		{
			player thread enable_wallrun(self);
		}
	}
}

function enable_wallrun(trig)
{
	self endon("death");
	self endon("disconnect");

	self.iswallrunning = true;
	while(self IsTouching(trig))
	{
		self AllowWallRun(true);
		WAIT_SERVER_FRAME;
	}
	self.iswallrunning = false;
	self AllowWallRun(false);
}
```

Save and close, rebuild the map. You can now use wallrunning.

---

_Contributors:_
- DTZxPorter
- RDV