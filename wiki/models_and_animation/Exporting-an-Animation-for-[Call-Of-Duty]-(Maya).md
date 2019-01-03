# Exporting An Animation For [Call of Duty] (Maya)

_Pre-first step: Always make sure your CodMayaTools are up-to-date from this link:_  [CodMayaTools](https://github.com/Ray1235/CoDMayaTools)

This tutorial goes over properly exporting an animation for the Call of Duty series in Maya.

> **NOTE:** Please take your time while following the steps, you'll likely encounter an error otherwise

This tutorial assumes you've already followed: [Proper Import](https://wiki.modme.co/TODO_LINK_IMPORT_TUTORIAL) or have already created a custom animation.

Next follow these instructions in-order:

- If you are exporting a **weapon anim**, continue below, otherwise skip to step 2
  - If you're exporting an animation that is **NOT** an `ads` you need to select the `tag_cambone` and the `tag_torso` tags (as shown) {F2537}
  - Then go to `Edit->Select Hierarchy`
  - If you're exporting an `ads` animation, you must select **ONLY** `tag_view` and `tag_torso`
  - If you've gotten here, skip to step 3.
- This applies to **none weapon** animations, continue below
  - Select `tag_origin` or whatever root bone your model has
  - After selecting the proper joints go to `Edit->Select Hierarchy` to select the child bones (as shown) {F2539}
  - Continue to step 3
- The file step is exporting the animation using **CodMayaTools** 
  - Go to `Call of Duty Tools->Export XAnim` and you will be presented with the export menu.
  - First, you must enter in the end frame time, as shown below you can find that time here: {F2541}
  - Enter that in the second box from the top (Will be shown below)
  - Next, either use the `Grab notes` feature to get notetracks, or enter them in manually.
  - Finally select a path to save the file using the `...` button. Below you'll see a completed export window {F2543}
  - Click on `Export Selection` to save the animation.

  ---

  _Contributors:_
  - DTZxPorter