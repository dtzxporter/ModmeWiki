# Setting Up Teleporters

*Setting up in Radiant*

- Download the prefabs and scripts then extract to `root/map_source` ([PREFABS / SCRIPTS](https://mega.nz/#!VJQQzbAA!WenlA62l8Pv9j7Q8b1sbOJPhkwJjQo5OS49wpeTmJy0)).
- Place at least one of all included prefabs that should now be in `root/map_source/_prefabs/zm/harrybo21_prefabs/`.
Extract the scripts into `root/usermaps/YOUR MAP NAME/scripts/zm/`

There are 6 prefabs: the three teleporters, the mainframe, a 'black box room' that the players are moved to for a short time while teleporting (this MUST be covered by a zone - but out of sight - you can have another copy of your starting zone covering this) and a Pack-a-Punch cage prefab, which is optional and is what blocks your access to the Pack-a-Punch until the teleporters are activated on The Giant.

*Setting up in script*

Open your `mapname.gsc` and find this:

```
#using scripts\zm\_zm_ai_dogs;
```

Underneath it put this:

```
#using scripts\zm\zm_giant_teleporter;
```

- Do the same in your `mapname.csc`.
- Open your maps `.zone` (right click your map in launcher and click `Open Zone File`).

Add this to the bottom:

```
scriptparsetree,scripts/zm/zm_giant_teleporter.gsc
scriptparsetree,scripts/zm/zm_giant_teleporter.csc
```

Recompile and test your map.

--- 

_Contributors:_
- Harry Bo21
- DTZxPorter