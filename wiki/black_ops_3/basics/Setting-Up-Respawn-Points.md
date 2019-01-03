# Setting Up Respawn Points

Download: [Everything You Need](https://mega.nz/#!0dkWkDoB!cbkmJlgLcP9xV-XSzHPGmVn1cSPmsbFdCZ9ukecE-2U)

- These are the points players can respawn in co-op games ( Or via my the Who's Who perk in Harrybo21's Perks )
- When a player respawns at the start of a round, the game will pick a location from these points - that is close to another player, so they wont keep respawning way back at the beggining

*Instructions*

- Download the files and extract them into your root directory ( Root directory is your Black Ops 3 install )
- This is the required prefab

*Radiant:*

- Place and stamp the prefab in your zone
- Select the center struct and open the KVPs ( press **N** )
- Change the `script_noteworthy` KVP to the zones `targetname`
- Repeat for whatever zones you want the players to be able to respawn in
- That is all for radiant

*You are DONE*

Ok, so assuming you've followed these steps exactly - you now just need to recompile your map and link in launcher. Now go test!

_Contributors:_
- Harry Bo21
- DTZxPorter