#Black Ops III: Attachment Setup - Tutorial=

#Credits
If you are using this tutorial, please credit these people:
- DTZxPorter
- JerriGaming
- Marvel4 (if you download his stringtable pack)
- Scobalula (if you use HydraX to get the stringtables)
- The Black Death

#Introduction
Black Ops III (and Black Ops II) use a setup for attachments which allows users to apply attachments with the console (weaponname+attachment+attachment...) and customize weapons to have attachments (either levelcommon or weapon kits), without the need for additional weaponfiles. This tutorial intends to document this setup and guide users to give their weapon ports this capability. It's not recommended to use this in a standalone map unless you plan on configuring weapon kits, as you will likely have a set idea of what you will use on your gun and can set it up in your weaponfile.

NOTE: This tutorial will be updated if more knowledge comes to light

#Contents
- Prerequisites
- Setting up the weapon in Maya
-- Porter's Weapon Info Dump
-- Setting up the skeleton and animations to work with attachments
- Into the Mod Tools
-- Quirks to be aware of
-- Attachment Unique assets
-- Attachment organization
-- Attachment specifics
-- Attachment assets
-- Pack a Punched version
- In-game
-- Zone file
-- Getting Black Ops III to load the attachments

#Prerequisites
Before starting the tutorial, you need the following dumps:

  *Porter's Weapon Info Dump**
[[Download|http://modme.co/index.php?view=topic&tid=856&page=1]]
  *Black Ops III Stringtables**
Source 1: Marvel4's dump
[[Download|https://drive.google.com/file/d/0BxNxXL3z8i1GcGNMSm1oVjltaVE/view]]

or Source 2: Rip them using Scobalula's HydraX
[[Download|https://github.com/Scobalula/HydraX]]

It is also recommended to have a good level of Maya and APE knowledge. If this is one of your first ports in general you should come back to this tutorial when you are more experienced.
#Setting up the weapon in Maya
Before you can setup your weapon's attachments to work in-game, you need to include all of your weapon's animated attachments in the skeleton to ensure they animate as desired in-game. This section will detail on how to do so.

# Porter's Weapon Info Dump
Download link: [[Porter's Weapon Info Dump|https://aviacreations.com/modme/index.php?view=topic&tid=856]]

To get the attachment offsets of a weapon download Porter's dump and find the dump files beginning with `au_`, in the `dumpsweaponinfo_mp` folder.

IMPORTANT: Do not use the attachment files in the `dumpsweaponinfo_zm` folder, as these appear to be missing values

An example attachment unique file would be `au_smg_msmc_extclip`. This is Extended Mags for the XMC. Open the file:
{F22342}
You should be greeted with a file similar to this.

Depending on the attachment, it may use `attachment[1]` only or both attachments. Generally, combined attachments (e.g. extclip+fastreload) use both of these attachment slots, whereas a single attachment (e.g. quickdraw) only uses one. There are exceptions to this rule however.

NOTE: Treyarch appear to always use `attachment[1]`, so if it has no offsets it is likely that it is a child of a specific joint. The KVK 99m does this with Long Barrel.

The offsets are provided in this format: `attachment[number] (forward, right, up) | (pitch, yaw, roll)`. The first three offsets are scaled in cm, and the last three are in degrees. Maya uses the same measurements, however before putting the first three offsets into APE, you will need to convert them into inches (offset divided by 2.54).

NOTE: You can establish the structure you need for your Attachment Unique assets from Porter's dump, single attachments are derived under `none` and `attachment1+attachment2` files are derived under `attachment1`'s Attachment Unique asset.

# Setting up the skeleton and animations to work with attachments
When creating the skeleton for your weapon (also known as the animated model - or animmodel), you need to include **all** animated attachments rigged to the weapon with the correct joints. These include but are not limited to: Extended Mags, Fast Mags and Rapid Fire. Some weapons animate more attachments (such as the KVK 99m, which animates its Long Barrel). Beware of this.

NOTE: This tutorial will not provide information on how to rig the animated attachments to the weapon, as it is expected you have reasonable Maya knowledge if you are following this guide.

Your weapon should look somewhat similar to this when the animated attachments have been added: (This is the XMC)
{F22909}

The reason you have to do this process is because the skeleton needs to know what to animate - and if there are joints missing when an animation is imported they will not be animated. Once you have setup your skeleton correctly, port over all of your animations like you would with any weapon.

#Into the Mod Tools

#Quirks to be aware of
  *Attachment we weren't given in the tools**
We were not given `damage` (High Caliber) or `ir` (Thermal) in the Mod Tools (we only got the Kuda's attachments). Note that you will need to port the Thermal's models yourself.

To create the missing `damage` attachment, you can derive the `defaultattachment` and seemingly keep it identical. For High Caliber, it appears Treyarch handle the changes in multipliers within the Attachment Unique asset.

  *Fatal Error - Weapon attachment (name) not found**
When you first try to load your attachments in-game (assuming it's a Black Ops III weapon), you likely will be greeted with an error saying:

  *
UNRECOVERABLE ERROR:
    Weapon attachment (attachment_name) not found

Linker will now terminate.
  *

NOTE: You can bypass having to repeatedly link by looking in the attachmentmappingsTable.csv file (see **Getting Black Ops III to load the attachments**), as all Black Ops III weapons have their attachments listed there.

Do not be alarmed. This error simply means there is an attachment asset that the weapon you are porting uses which is missing from APE, and is also not loaded in by the game.

To solve this issue, open APE and locate the GDT weaponattachments:
{F22918}

Within this GDT are all the attachments that Treyarch gave us within the Mod Tools (however a few more are loaded for us aswell). Simply find the base of the attachment you are missing (for example: `fastreload_msmc` is the attachment you are missing, so find `fastreload`) and derive it, calling it the attachment you are missing.

You can use Marvel4's Black Ops III stats dump to retrieve the attachment's stats: [[Dump Link|https://docs.google.com/spreadsheets/d/1k7jVpX782zoAIDGqj61l1Yw5qoPf1QVHpM01mwa-tTI/edit#gid=546409744]].

Once this is completed, the missing attachment error should no longer occur. You do not need to put the attachment into your zone file.

  *Certain attachments choosing not to work**
NOTE: This issue only seems to occur with Black Ops III weapons

There also seems to be an issue with certain attachments not working in-game, without an error.

While it is currently unknown what causes this issue, the solution is relatively simple. Find the attachment asset in APE which is not working (e.g. `extclip`), and derive it, calling it something similar (such as `extclip_fix`). Ensure you refer to this derived attachment in your attachment mappings table also (see **Getting Black Ops III to load the attachments**) and once this has been completed your attachment should work fine in-game.

#Attachment Unique assets
Attachment Unique assets do what they say, they specify the unique features of a gun's attachment. Treyarch use these to change animations, apply xmodels, hide tags or set other unique features that would not be able to be generalized with an attachment asset.

  *Structure**
The Attachment Unique structure uses a base asset (suffixed `_none`) with all attachments derived from it.

Create an `attachmentUnique` asset in your GDT. A rule of thumb of what to call it is `au_weaponname_none`, however other naming schemes are possible with `Attachment Unique Base` (see **Pack a Punched Version**). This is an example of a base Attachment Unique asset:
{F23843}

IMPORTANT: Do not remove the `_none` suffix on your base Attachment Unique asset.

From here, you can derive each of your weapon's attachments under `_none`, giving them suffixes like `_extclip`, `_fastreload` among others. You can use Porter's Weapon Info Dump to establish the attachments available on your weapon.

You will likely encounter multiple attachments being used in one file, such as:
{F23845}

For these assets you should derive them under their first attachment, in the KVK 99m's (AN-94's) case being `_extclip`. It should look like this:
{F23847}

This lets the game know that when these attachments are used simultaneously it should use this asset instead of their respective ones, which would likely conflict.

NOTE: Extended Mags, Fast Mags, Grip and Rapid Fire with Suppressor do not follow this rule. See **Attachment specifics**.

  *Setup**
Now that your structure is setup, you need to configure your `attachmentUnique` assets.

At the top of your Attachment Unique asset, you will find `attachmenttype`. Override it and set it to the attachment this asset is for. Example (AN-94 Extended Mags):
{F23849}

NOTE: Attachment Unique assets handling more than one attachment use the second attachment as the `attachmenttype`.

You can override `Hide Tags` to hide any joints (and meshes binded to them) which an attachment gets rid of (such as iron sights when using optics).

NOTE: Many games use a `tag_sight_off` and `tag_sight_on` system (or similarly named) where `off` is hidden when the player is using iron sights and `on` is hidden when the player is using an optic. Ensure that you put `tag_sight_off` (or however it is named for the gun) in your root Attachment Unique asset and change it accordingly to its `on` counterpart for any optic Attachment Unique asset.

The `XAnims` category allows you to override any animations used on the base weapon which an attachment changes (such as Grip).

The `Attachment #number` sections allow you to specify the xmodel assets that an attachment adds:
{F23851}

`Attachment Association`: the attachment xmodel(s)' association

`Attachment View Model`: the 1st person xmodel asset that you want to be shown
`ADS View Model`: the 1st person xmodel asset that you want to be shown when the player is in ADS (primarily ACOG or other scopes)
`Attachment View Model Tag`: the joint you want the attachment xmodel to be a child of - defaults to `tag_weapon`
`Attachment View Offset`: the offsets from the origin of the parent's joint - use Porter's Weapon Info Dump to obtain this information (convert to inches!)
`Attachment View Model Offset Angles`: the angle offsets from the parent's joint - use Porter's Weapon Info Dump to obtain this information (no conversion needed)

`Attachment World Model`: the 3rd person xmodel asset that you want to be shown
`Attachment World Model Tag`:  the joint you want the attachment xmodel to be a child of - defaults to `tag_weapon`
`Attachment World Offset`: the offsets from the origin of the parent's joint (Porter's Weapon Info Dump does not provide this information, but they are generally the same as the 1st person offsets)
`Attachment World Model Offset Angles`: the angle offsets from the parent's joint (Porter's Weapon Info Dump does not provide this information, but they are generally the same as the 1st person offsets)

#Attachment organization
NOTE: This section is not required, however it is highly recommended to pay attention to it in order to prevent conflicts with ports

In order to prevent major conflicts between weapon ports by authors, it is highly recommended not to provide any attachments within the `weaponattachments` GDT. Keep it stock.

You can derive a custom attachment asset within the `weaponattachments` GDT, set it up to how you desire then move it into a separate, custom GDT which should prevent GDT conflicts with various ports.

#Attachment specifics
Some attachment unique assets are much less plug and play to setup. This subheading will provide information for those in question.

  *Extended Mags (extclip) or Fast Mags (fastreload) or both**
For Extended Mags or Fast Mags, you can setup the Attachment 1 model as normal (and its offsets will likely be identical to the base magazine model). However, there is one extra attribute to check:
{F22922}
This tells the game to disable the base magazine attachment set in the weaponfile (//whether it works with the viewmodel being combined with the magazine viewmodel is unverified//).

When handling both (which is normally derived from `extclip` as `extclip+fastreload`, you might need to specify a fast mags attachment as Attachment 2 or use `ext_fast_mag` as Attachment 1. This depends on the weapon. You also generally need to specify the Fast Mag reload animations, however it is possible certain weapons have dedicated extended fast mag reloads.

  *Varix 3 (dualoptic)**
Varix 3's Attachment Unique asset is setup like any other attachment except that you need to specify an Alt Weapon Name (dualoptic_weaponname).

IMPORTANT: Never use a weapon's mode suffix when specifying an `Alt Weapon Name` (these suffixes being `_zm`, `_mp`, or `_cp`).

Ensure, still within the Attachment Unique asset, that your equivalent for these animations are specified:
{F22925}

Now that you have completed the part within the Attachment Unique asset, you now need to derive your weapon's weaponfile and name it `dualoptic_YOURWEAPONNAMEHERE`.

NOTE: Ensure that within your non-dualoptic weaponfile that `Alt Weapon Name` is not specified, and `Ads Only Alt Weapon` and `Disable Toggle Weapon Switching` are checked. These can be found under `Alt Mode Options`.

Within your `dualoptic_` weaponfile, you need to specify `Alt Weapon Name` as your original weaponfile's name and make sure your weapon's equivalent of these animations are specified in `XAnims`:
{F22928}

Make sure to include the dualoptic weaponfile in your zone file (`weaponfull,dualoptic_WEAPONNAME`).

Varix 3 should now work for your weapon.

  *Special Combo - Extended Mags, Fast Mags and Grip**
For this case, there are no extra Attachment Unique assets needed. Simply, within your weaponfile, specify your weapon's equivalent of the following animations:
{F22930}

  *Suppressor (suppressed)**

Using loop sounds:
Find `Sounds` in your Attachment Unique asset. Specify these following sounds:
{F22934}

Not using loop sounds:
Find `Sounds` in your Attachment Unique asset. Specify these following sounds:
{F22936}

  *Rapid Fire (rf)**
NOTE: This step isn't required if you're not using loop sounds

Find `Sounds` in your Attachment Unique asset. Specify these following sounds:
{F22934}

  *Rapid Fire and Suppressor**
NOTE: This step isn't required if you're not using loop sounds

Like the special combo, no additional Attachment Unique assets are needed. In order to get sounds to work with Rapid Fire and a Suppressor, specify these sounds in your weaponfile:
{F22932}

#Attachment assets
Attachment assets are responsible for changing your weapon's stats but also are what you put in your `attachmentmappingsTable.csv` to get your attachments to load.

NOTE: Unless you want your weapon to have a unique set of attachment stats (or you have attachments that aren't loading in), you can ignore this section

Find the GDT `weaponattachments`. It should look something like this:
{F23840}

Inside are all the attachments we were given in the Mod Tools. To create a different version of an attachment, you can derive it, and name it `originalattachment_useforderivedversion`. This will allow you to keep the stats of the attachment it is based off but then edit anything you need to. For example, if I wanted to create the Extended Mags attachment used for the KVK 99m, I could derive `extclip`, calling it `extclip_an94`. I can then right click on a value in the derived asset and change it to how I want it.

NOTE: If you are creating attachments for Black Ops III weapons which you are missing, you can use Marvel4's stat dump to find the differences associated with that given attachment.

After you have setup your attachment, it is highly recommended to move the attachment out of the `weaponattachments` GDT (see **Attachment organization**). You can now call this attachment in your `attachmentmappingsTable.csv` and it will load in with those stats.

#Pack a Punched Version
In order to get your Pack a Punched weapon to load in attachments, you will need to set its `Attachment Unique Base`. This is found within the weaponfile, under `Misc`. To set this, you need to omit the suffix of your base Attachment Unique asset. For example, if the base Attachment Unique asset is `au_ar_an94_none`, you should put `au_ar_an94` as your `Attachment Unique Base`.

NOTE: You can use Attachment Unique Base for your non-Pack a Punched weapon also if the name of your Attachment Unique assets are obscure.

#In-game
Now that you have setup everything in APE, there are just a few more things to do to get your attachments working.

#Zone file
When putting your weapon into your zone file, you need to specify `weaponfull` instead of `weapon` (wow Sp33dy, you actually have an excuse to use it now). This tells Black Ops III to load in your weapon's attachments (and cosmetics if you put those in too).

Linker should convert the attachments if you have setup everything else correctly. However, if you load in fine but you cannot use any of your attachments, you have not added your weapon to the attachment mapping table (see **Getting Black Ops III to load the attachments**).

#Getting Black Ops III to load the attachments
As long as you installed Marvel4's BO3 Stringtables, you should have a file called `attachmentmappingsTable.csv` under `share/raw/gamedata/weapons/common`. Open it:
{F23853}

Do not be alarmed. This file is actually quite simple, you merely have to specify the weapon name as the first parameter, and list all `attachment` assets it uses as the second parameter, each divided by a space.

Copy a line that is somewhat similar to your weapon's and adjust it to how you need it.

Example:
{F23855}

You will also need to do a line for your weapon's upgraded version - and a line for dualoptic is not required.

NOTE: All Black Ops III customizable weapons are already provided in this file, but you will need to create a line for their Pack a Punched version if they were not featured in Zombies

#You are finished!=
As long as I haven't messed something up with this tutorial, your weapon should now have working attachments!