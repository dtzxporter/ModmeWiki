Below is a list of shellshocks loaded in the ffs for Black Ops 3

Some of them are loaded in MP, ZM or CP only, so if they dont seem to work, the one you chose may not be loaded in your current game mode

Use them with the following functions ( Found in the API provided with the mod tools )


<player> ShellShock(<shellshockname>,<duration>,[allowReduceShellShockPerk])
[MANDATORY] <shellshockname>
[MANDATORY] <duration> duration in seconds. The duration must be between 0 and 60 seconds.
[OPTIONAL] [allowReduceShellShockPerk] true if shell shock perk should be reduced
CATEGORY: 
CLIENT/SERVER: Server
SUMMARY: Start a shell shock sequence for the entity for given duration.
EXAMPLE: self shellShock( "frag_grenade_mp", 0.2 )

<player> StopShellShock()
CATEGORY: 
CLIENT/SERVER: Server
SUMMARY: Stops the shell shock sequence for the player
EXAMPLE: player StopShellShock()



concussion_grenade_mp
damage_mp
dog_bite
emp_shock
flare_mp
flashbang
frag_grenade_mp
heat_wave
hold_breath
hold_breath_mp
lightninggun
mortarblast_enemy
mortarblast_friendly
mp_radiation_high
mp_radiation_low
mp_radiation_med
pain
proximity_grenade
proximity_grenade_exit
shock_field
straferun
tabun_gas_mp
tabun_gas_nokick_mp
tankblast_mp
victoryscreen
weapon_butt
default
resurrect
explosion
shellshock,grief_stab_zm
pain_zm
shellshock,zombie_death
electrocution
