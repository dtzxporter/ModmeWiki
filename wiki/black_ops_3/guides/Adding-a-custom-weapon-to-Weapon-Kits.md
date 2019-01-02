NOTE: Before starting this tutorial, you will need to obtain a copy of these files: `zm_gunlevels.csv`, `mp_attributestable.csv`, `mp_statstable.csv`, `cp_statstable.csv` and `zm_statstable.csv`. Here is a download with the files in: [[Download|https://mega.nz/#!zBtCyJ5L!MMhLc1ddeLSMSuLpIdTIquK_rAFpFvF9tpyVwW60raM]] (Credit Scobalula for providing the means to obtain these tables)

IMPORTANT: This cannot be achieved in a standalone map, you will need an accompanying mod to go with it.

  *//Contents//**
- Multiplayer weaponfile
- XCam
- Adding statstable entries
- Gun levelling
- Stats bar

---
  *Multiplayer weaponfile**
NOTE: Your zombie weaponfile must have the suffix `_zm` on the end or Weapon Kits will not behave properly.

In Weapon Kits, Black Ops III uses the multiplayer weaponfile of a weapon for display in Weapon Kits and for customization. Therefore, to have your weapon actually appear and be customizable properly in Weapon Kits, you need to create a multiplayer weaponfile for it. Derive (or duplicate) your `_zm` weaponfile and change its suffix to `_mp`. Whether you want to change any features for the MP weaponfile is up to your discretion.

  *XCam**
The 3D preview of your weapon is positioned by an XCam - and so you will need to specify one in your weaponfile so the weapon is positioned properly. Note that Black Ops III does still put an XCam on even if you don't specify one, however there is a noticeable difference in position.

You could either use (and perhaps slightly edit) the AP9 (Kuda) XCam for your weapon or you can create your own XCam, however that will not be documented in this guide.

In your weaponfile, find under Misc the following settings: `CAC Weapon XCam` and `CAC Attachments XCam`. Set both to your custom XCam or the AP9's XCam (`ui_cam_cac_smg_standard`).

  *Adding statstable entries**
NOTE: You can find a CSV prepared by Harry Bo21 which references the columns of the statstable and what they do here: [[Modifying Zombies Weapon Kits|http://phabricator.aviacreations.com/w/black_ops_3/basics/modifying_zombies_weapon_kits/]]

This section will focus on the following CSV files: `zm_statstable.csv`, `mp_statstable.csv` and `cp_statstable.csv`.

You can edit the mode statstable files to your need. Add, remove or replace weapons in there as you please, however beware that **on online mode, you must have at least one weapon in each section of Weapon Kits or you will get a UI error.**

Here is an example entry of a custom weapon put into Weapon Kits:
`12,,weapon_smg,WEAPON_S2_GREASE_GUN,smg_grease_gun_s2,,s2_icon_weapon_greasegun,WEAPON_S2_GREASE_GUN_DESC,reddot quickdraw reflex grip steadyaim fmj extbarrel extclip rf suppressed,1,0,,1,primary,,,,1,,,`

`12`: The index. You can set this to any number that is free but note that there is a 255 entry limit in the table. Ensure this index is the same as the weapon's index in the multiplayer statstable.

`weapon_smg`: The class of the weapon. This will determine how many attachments can be applied and what section of Weapon Kits the weapon will appear in.

`WEAPON_S2_GREASE_GUN`: The localized name of the weapon. You must use localization when making Weapon Kits entries.

`s2_icon_weapon_greasegun`: The icon of the weapon which appears when you are in the list of weapons in a section. This will correspond to an image name in APE - you can set this up and then you must add an entry into your zone file so the image is loaded.

`WEAPON_S2_GREASE_GUN_DESC`: The localized description of the weapon. You must use localization when making Weapon Kits entries.

`reddot quickdraw reflex grip steadyaim fmj extbarrel extclip rf suppressed`: The attachments that are available on the weapon, **in the order that they will be unlocked in**. If your weapon does not have attachments, leave this blank.

First `1`: The position in order the weapon will appear in the class' list. `1` is the top, and an increasing number goes further down the list.

`0`: The level that you unlock the weapon at. **As you cannot level up in a mod, you should always keep this at 0, or your weapon will appear locked.**

Second `1`: Whether the weapon should appear in Weapon Kits or not. `1` means appear, `-1` means hidden.

`primary`: The inventory that the weapon is in. This can be: `primary`, `secondary` or `equippedbubblegumpack` in zombies.

You can edit this example entry or create a different entry to your own specification. The different stats tables can have identical entries unless you specifically want them to be different.

  *Gun levelling**
NOTE: If your weapon does not have any attachments, you can ignore this section.

This section will focus on the following CSV file: `zm_gunlevels.csv`

In order to unlock attachment options for your weapon, you will need to add some entries to this file to tell the game to unlock them. As we cannot make practical use of the specific settings, they will not be documented in this guide. Here is a pre-prepared set of entries that will unlock all attachment options for you:


1,0,smg_mas38_s2,,,0
2,0,smg_mas38_s2,,,1
3,0,smg_mas38_s2,,,2
4,0,smg_mas38_s2,,,3
5,0,smg_mas38_s2,,,4
7,0,smg_mas38_s2,,,5```

Each level in that entry is specifying for the game to unlock a specific attachment slot. `0` is your optic slot, and `1-5` are your attachment slots. Should you need to, you can remove any number of these.

  *Stats bar**
This section will focus on the following CSV file: `mp_attributestable.csv`

To set up the stats bar for your weapon (the stats saying damage, range, fire rate and accuracy), you will need to add an entry to the attributes table:
`weapon_assault,ar_example,accuracy,damage,range,firerate,0,25,MPUI_FULL_AUTO,`

Substitute in the numbers of your weapon's stats (Black Ops III works from 0-100 in its stats bar, where every 5 is a full box). `weapon_assault` is your class, you will need to edit this depending on the type of weapon you are adding, and you also will need to change `MPUI_FULL_AUTO` to `MPUI_SEMI_AUTO` if your weapon is semi auto.

---
  *//Contributors//**
JerriGaming
The Black Death
Scobalula
Harry Bo21