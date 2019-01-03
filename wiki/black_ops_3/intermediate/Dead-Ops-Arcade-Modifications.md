# Dead Ops Arcade Mods

### Modifying Dead Ops Arcade with mods
This will go over setting up a modification for dead ops arcade.

> **WARNING:** This tutorial requires that you have L3akMod installed!

## Setting up the mod
Create a new game mod, name it whatever, and build using the `cp_mod` setting in the launcher. Open up your `cp_mod.zone` and add the following lines:
```php
// Override the file, providing us with a bootstrap for DOA
scriptparsetree,scripts/shared/doagmt_bootstrap.csc
scriptparsetree,scripts/shared/doagmt_bootstrap.gsc
scriptparsetree,scripts/cp/_doa_usermap.csc
scriptparsetree,scripts/cp/_doa_usermap.gsc
scriptparsetree,scripts/cp/doa/_doa_core.gscc
scriptparsetree,scripts/cp/doa/_doa_core.cscc
```
These names **must** be the same, and we will be modifying the contents later.

## Getting the files
Download the following zip: [DeadOpsArcade](https://mega.nz/#!RVJBTayI!UNxBybFhMThNvGoqBxi4DnMk8zjztUyqHHesCAlWjio) and extract the folder structure to the root of your install path.

## Adding your own code
Find either _doa_usermap.csc or _doa_usermap.gsc and add whatever client script or server script code you would like. The `init()` function will be called as usual once you load the level. This code is providing a bootstrap around the exsiting game.

> **WARNING:** It is important to keep the file names as the precompiled scripts are hardcoded! Add custom code to the _usermap file ONLY!

## Final notes
The Dead Ops hud **does not** have the elements for iPrintLn so you can't use prints for debugging, it is recommended that you override the `t7hud_doa.lua` file and create your own widgets for debugging.