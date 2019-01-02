Download: [[Everything you need|https://mega.nz/#!JBFiSChS!vFjGoob1UT5YYYi-NDYcO8Pld1pNv8KIu6LCPx6sfe8]]

  *Instructions**

    - Download the files and extract them into your root directory ( Root directory is your Black Ops 3 install )
    - Now for actually implementing the fix, there is actually two possible ways you can do this, I will list both below

  *Method 1 : Adding a call to the alias I provided in your SZC file**

    - Every map or mod uses these files, if its a mod, youd need to create one i believe. In this tutorial we will assume however you are making a map.
    - Navigate to your maps folder !!root/usermaps/YOUR_MAP!!
    - Now go to !!sound/zoneconfig!!
    - You will find a SZC file in here, named after your map

{F2545}

    - Open this file with a text editor and you will see something like this

{F2547}

    - This is a horribly formatted file, so be careful to follow the instructions carefully from here.
    - Find this block of text


"Sources" : [
    {
    "Type" : "ALIAS",
    "Name" : "user_aliases",
    "Filename" : "user_aliases.csv",
    "Specs" : [ ] 
 },


    - Underneath it, simple paste this text


{
 "Type" : "ALIAS",
 "Name" : "perk_sounds",
 "Filename" : "perk_sounds.csv",
 "Specs" : [ ] 
},


    - So it should look like this :

{F2549}

    - Thats it, just link your mod in launcher and everything should be done. You would repeat this for any map or mod you make, as the changes only effect the map  which you edited the SZC file for

  *Method 2 : Adding the required fields to the alias used by your maps**

    - Navigate to !!root/share/raw/sound/aliases!! and open the file called !!user_aliases.csv!! with a text editor
    - All you would need to do is copy the text !!except for the top line!! from the alias i provided ( if you copied the files already it will also be in here "perk_sounds.csv" ) into this file. To save you the trouble however i will post this below: 
    - Once this is done, you simply need to link your map in launcher again. This change will effect any maps you have made or will make, as this alias is called by default in them



1. PERKS,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
evt_belch,,,zombie\perks\perkacola\burp.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
evt_perk_swallow,,,zombie\perks\perkacola\swallow.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
evt_perk_deny,,,zombie\perks\perkacola\deny.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
evt_bottle_dispense,,,zombie\perks\perkacola\dispense.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
evt_perk_bottle_open,,,zombie\perks\perkacola\open.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
evt_bottle_break,,,zombie\perks\perkacola\break.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_power_on,,,zombie\perks\machine\power_on.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,700,701,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_machine_loop,,,zombie\perks\machine\hum_loop.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,60,60,50,350,351,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,LOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. PACKAPUNCH,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_packa_knuckle_0,,,zombie\pack_a_punch\knuckle_00.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_packa_knuckle_1,,,zombie\pack_a_punch\knuckle_01.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_packa_upgrade,,,zombie\pack_a_punch\upgrade.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_packa_ready,,,zombie\pack_a_punch\ready.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_packa_loop,,,zombie\pack_a_punch\pap_loop.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,LOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_packa_ticktock,,,zombie\pack_a_punch\loop.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,LOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_packa_deny,,,zombie\pack_a_punch\deny.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_packa_jingle,,,zombie\pack_a_punch\mus_packapunch_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_packa_sting,,,zombie\pack_a_punch\mus_packapunch_sting.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. QUICKREVIVE,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_revive_sting,,,zombie\perks\mus\mus_revive_sting.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_revive_jingle,,,zombie\perks\mus\mus_revive_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. JUGGERNOG,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_jugganog_jingle,,,zombie\perks\mus\mus_jugganog_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_jugganog_sting,,,zombie\perks\mus\mus_jugganog_sting.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. DOUBLETAP,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_doubletap_jingle,,,zombie\perks\mus\mus_doubletap_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_doubletap_sting,,,zombie\perks\mus\mus_doubletap_sting.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. SPEEDCOLA,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_speed_jingle,,,zombie\perks\mus\mus_speed_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_speed_sting,,,zombie\perks\mus\mus_speed_sting.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. DEADSHOT,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_deadshot_jingle,,,black_ops_2\perks\deadshot\mx_deadshot_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_deadshot_sting,,,black_ops_2\perks\deadshot\mx_deadshot_sting.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. STAMINUP,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_stamin_jingle,,,black_ops_2\perks\staminup\mx_staminup_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_stamin_sting,,,black_ops_2\perks\staminup\mx_staminup_sting.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. PHD,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_phdflopper_jingle,,,black_ops_2\perks\phd\mx_phd_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_phdflopper_sting,,,black_ops_2\perks\phd\mx_phd_sting.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

zmb_perks_phdflopper_explode,,,black_ops_2\perks\phd\explosion_00.wav,,,UIN_MOD,,,,,,,,,0,0,100,100,0,1000,1000,,,,,,,,,,,,,,,,3d,front,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. MULEKICK,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_mulekick_jingle,,,black_ops_2\perks\mulekick\mx_mule_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_mulekick_sting,,,black_ops_2\perks\mulekick\mx_mule_sting.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. TOMBSTONE,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_tombstone_jingle,,,black_ops_2\perks\tombstone\mx_tombstone_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_tombstone_sting,,,black_ops_2\perks\tombstone\mx_tombstone_sting.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. WHOSWHO,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_whoswho_jingle,,,black_ops_2\perks\whos_who\whoswho_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_whoswho_sting,,,black_ops_2\perks\whos_who\whoswho_short.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

zmb_perks_whoswho_begin,,,black_ops_2\perks\whos_who\mx_whoswho_begin.wav,,,UIN_MOD,,,,,,,,,0,0,100,100,0,131070,131070,,,,,,,,,,,,,,,,2d,front,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_whoswho_loop,,,black_ops_2\perks\whos_who\ww_looper.wav,,,UIN_MOD,,,,,,,,,0,0,80,80,0,131070,131070,,,,,,,,,,,,,,,,2d,front,,LOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_whoswho_deactivate,,,black_ops_2\perks\whos_who\ww_deactivate.wav,,,UIN_MOD,,,,,,,,,0,0,100,100,0,131070,131070,,,,,,,,,,,,,,,,2d,front,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. ELECTRICCHERRY,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_cherry_jingle,,,black_ops_2\perks\electriccherry\mx_electric_cherry_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_cherry_sting,,,black_ops_2\perks\electriccherry\mx_electric_cherry_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. VULTUREAID,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_vulture_jingle,,,black_ops_2\perks\vulture\mx_vulture_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_vulture_sting,,,black_ops_2\perks\vulture\mx_vulture_sting.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

zmb_perks_vulture_drop,,,black_ops_2\perks\vulture\drop.wav,,,UIN_MOD,,,,,,,,,0,0,100,100,0,1000,1000,,,,,,,,,,,,,,,,3d,front,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_vulture_loop,,,black_ops_2\perks\vulture\loop.wav,,,UIN_MOD,,,,,,,,,0,0,40,80,0,1000,1000,,,,,,,,,,,,,,,,3d,front,,LOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_vulture_money,,,black_ops_2\perks\vulture\money.wav,,,UIN_MOD,,,,,,,,,0,0,100,100,0,1000,1000,,,,,,,,,,,,,,,,3d,front,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_vulture_pickup,,,black_ops_2\perks\vulture\pickup.wav,,,UIN_MOD,,,,,,,,,0,0,100,100,0,1000,1000,,,,,,,,,,,,,,,,3d,front,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

zmb_perks_vulture_stink_start,,,black_ops_2\perks\vulture\stink\start.wav,,,UIN_MOD,,,,,,,,,0,0,100,100,0,1000,1000,,,,,,,,,,,,,,,,3d,front,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_vulture_stink_loop,,,black_ops_2\perks\vulture\stink\loop.wav,,,UIN_MOD,,,,,,,,,0,0,80,100,0,100,100,,,,,,,,,,,,,,,,3d,front,,LOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
zmb_perks_vulture_stink_stop,,,black_ops_2\perks\vulture\stink\stop.wav,,,UIN_MOD,,,,,,,,,0,0,100,100,0,1000,1000,,,,,,,,,,,,,,,,3d,front,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

1. WIDOWSWINE,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_widow_jingle,,,black_ops_2\perks\widowswine\ww_jingle.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
mus_perks_widow_sting,,,black_ops_2\perks\widowswine\ww_sting.wav,,,UIN_MOD,,,,,BUS_FX,,,,,,75,75,50,400,401,,,,,3,oldest,,,1,1,,,,,,3d,wpn_all,,NONLOOPING,,,,,,,,,,,,,,,,,,,,,,,,,,,YES,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,



  *Contributors**
Harry Bo21
DTZxPorter
Redspace200