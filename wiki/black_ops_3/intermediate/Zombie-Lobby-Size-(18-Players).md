# Zombie Lobby Size (18 Players)

## Increasing the zombie lobby size
This will cover modifying game scripts to support more than 4 players. This tutorial assumes you know how to modify core game scripts.

## Modifying _zm.gsc
Find the following:
``` php
level.player_too_many_players_check = true;
```
And change it to:
``` php
level.player_too_many_players_check = false;
```
Next, find:
``` php
		case 4:
			n_delay = 0.67;		// 0.95 == 0.1 @ round 60
			break;
```
And change it to:
``` php
		default:
			n_delay = 0.67;		// 0.95 == 0.1 @ round 60
			break;
```

## Modifying _zm_laststand.gsc | .csc
Find the following loops in each file under __init__:
``` php
for( i = 0; i < 4; i++ )
```
And change the number '4' to however many players you want to allow:
``` php
for( i = 0; i < 18; i++ )
```
Next find:
``` php
level.player_name_directive=[];
level.player_name_directive[0] = &"ZOMBIE_PLAYER_NAME_0";
level.player_name_directive[1] = &"ZOMBIE_PLAYER_NAME_1";
level.player_name_directive[2] = &"ZOMBIE_PLAYER_NAME_2";
level.player_name_directive[3] = &"ZOMBIE_PLAYER_NAME_3";
```
And add as many slots as you need to the array:
``` php
level.player_name_directive=[];
level.player_name_directive[0] = &"ZOMBIE_PLAYER_NAME_0";
level.player_name_directive[1] = &"ZOMBIE_PLAYER_NAME_1";
level.player_name_directive[2] = &"ZOMBIE_PLAYER_NAME_2";
level.player_name_directive[3] = &"ZOMBIE_PLAYER_NAME_3";
level.player_name_directive[4] = &"ZOMBIE_PLAYER_NAME_4";
level.player_name_directive[5] = &"ZOMBIE_PLAYER_NAME_5";
level.player_name_directive[6] = &"ZOMBIE_PLAYER_NAME_6";
level.player_name_directive[7] = &"ZOMBIE_PLAYER_NAME_7";
...
```

Don't forget to precache them:
```
#precache( "string", "ZOMBIE_PLAYER_IS_REVIVING_YOU", "ZOMBIE_PLAYER_NAME_0" );
...
```

## Modifying zclassic.gsc | zclassic.csc
Add the following under __init__ in the GSC file:
``` php
	for ( i = 4; i < 18; i++ )
	{
          // Hardcoded clientfields per-player, each require a bitlen of 3.
		clientfield::register( "clientuimodel", "PlayerList.client" + i + ".score_cf_damage", VERSION_SHIP, GetMinBitCountForNum( 7 ), "counter" );
          clientfield::register( "clientuimodel", "PlayerList.client" + i + ".score_cf_death_normal", VERSION_SHIP, GetMinBitCountForNum( 3 ), "counter" );
          clientfield::register( "clientuimodel", "PlayerList.client" + i + ".score_cf_death_torso", VERSION_SHIP, GetMinBitCountForNum( 3 ), "counter" );
          clientfield::register( "clientuimodel", "PlayerList.client" + i + ".score_cf_death_neck", VERSION_SHIP, GetMinBitCountForNum( 3 ), "counter" );
          clientfield::register( "clientuimodel", "PlayerList.client" + i + ".score_cf_death_head", VERSION_SHIP, GetMinBitCountForNum( 3 ), "counter" );
          clientfield::register( "clientuimodel", "PlayerList.client" + i + ".score_cf_death_melee", VERSION_SHIP, GetMinBitCountForNum( 3 ), "counter" );
	}
```
Add the following for the __init__ in csc:
``` php
	for ( i = 4; i < 18; i++ )
	{
          // Hardcoded clientfields per-player, each require a bitlen of 3.
		clientfield::register( "clientuimodel", "PlayerList.client" + i + ".score_cf_damage", VERSION_SHIP, GetMinBitCountForNum( 7 ), "counter", undefined, !CF_HOST_ONLY, !CF_CALLBACK_ZERO_ON_NEW_ENT );
          clientfield::register( "clientuimodel", "PlayerList.client" + i + ".score_cf_death_normal", VERSION_SHIP, GetMinBitCountForNum( 3 ), undefined, !CF_HOST_ONLY, !CF_CALLBACK_ZERO_ON_NEW_ENT );
          clientfield::register( "clientuimodel", "PlayerList.client" + i + ".score_cf_death_torso", VERSION_SHIP, GetMinBitCountForNum( 3 ), undefined, !CF_HOST_ONLY, !CF_CALLBACK_ZERO_ON_NEW_ENT );
          clientfield::register( "clientuimodel", "PlayerList.client" + i + ".score_cf_death_neck", VERSION_SHIP, GetMinBitCountForNum( 3 ), undefined, !CF_HOST_ONLY, !CF_CALLBACK_ZERO_ON_NEW_ENT );
          clientfield::register( "clientuimodel", "PlayerList.client" + i + ".score_cf_death_head", VERSION_SHIP, GetMinBitCountForNum( 3 ), undefined, !CF_HOST_ONLY, !CF_CALLBACK_ZERO_ON_NEW_ENT );
          clientfield::register( "clientuimodel", "PlayerList.client" + i + ".score_cf_death_melee", VERSION_SHIP, GetMinBitCountForNum( 3 ), undefined, !CF_HOST_ONLY, !CF_CALLBACK_ZERO_ON_NEW_ENT );
```

> **NOTE:** DLC maps, and custom clientuimodels ALL need to be registered for your TARGET lobby size. Failure to do so will result in a hard crash.

_Contributors:_
- DTZxPorter
- Redspace200
- HarryBo21
- DidUKnowIPwn
- LilRobot