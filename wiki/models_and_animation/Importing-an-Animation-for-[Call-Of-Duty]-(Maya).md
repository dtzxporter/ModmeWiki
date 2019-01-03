# Importing An Animation For [Call of Duty] (Maya)

_Pre-first step: Always make sure your SE Tools are up-to-date from this link:_  [SE Tools](https://github.com/dtzxporter/SETools)

This tutorial goes over properly importing an animation for the Call of Duty series in Maya.

> **NOTE:** Please take your time while following the steps, you'll likely encounter an error otherwise

First, setup your scene with the model you'd like to animate, if you're doing a weapon animation you must have the `viewhands`, `viewmodel`, and in some games the `clipmodel` which should be aligned up to your best ability on the gun and also a child of `tag_weapon / j_gun`. (These must already have the skin binded using _BIND.mel or using SEModels which are already setup)

> **NOTE:** If you are opening the file, it is best to use File->Open to avoid namespaces as you may encounter issues importing that way.

Next follow these instructions in-order:

- If you are importing a **weapon anim**, continue below, otherwise skip to step 2
  - You must first bind the weapon properly to the players hand. SE Tools has a weapon binding tool at `SE Tools->Game Specific Tools->Call of Duty->Attach Weapon to Rig`
  - If the weapon doesn't move (Bind did not complete) it is likely that you have namespaces in the scene or you're using a custom rig. If you're **not** using a conversion rig, proceed to step C, else, continue to step D.
  - Before attempting to rebind, go to `SE Tools->Clean Namespaces` then attempt to attach the weapon again. If unsuccessful, continue to step D for manual binding.
  - Manually binding the model is easy, you must first find the base tag of the weapon [tag_weapon, j_gun] and find the base viewhands tag [tag_weapon_right, tag_weapon] to parent it to. In maya you must middle mouse click and drag the base weapon tag onto the base viewhands tag. Here is a video of doing that properly: {F2451} this next part is very important, you must select your `base weapon tag` and `base hand tag` and 0 out the properties, see the screenshots for more information, (BEFORE): {F2453} (AFTER): {F2455}
- If you made it here, you simply have to go to `SE Tools->Import SEAnim`, select the .seanim file and it will be imported into Maya.