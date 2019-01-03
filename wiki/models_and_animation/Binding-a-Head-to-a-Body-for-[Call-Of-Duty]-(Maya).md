# Binding A Head To A Body For [Call of Duty] (Maya)

*Binding the head*

For some body types where the head isn't attached to the body in the body model (Mostly zombie models) you can attach it to make it easier to work with.

*First step: Bind the head mesh*
- Import the head mesh into Maya and apply the bind file.
- Save the scene as `helmet_bound.ma (or mb).`

*Next step: Loading the scene*
- `File->Open` the body (This is done to remove namespaces)
- Drag on the `helmet_bound` file you saved earlier.
- Run the following mel script (save as binder.mel):

``` php
// Stage 1: Bind helmet

parent helmet_bound:j_spine4 j_spineupper;

// Stage 1.1: Get pos

float $findMEX = `getAttr("j_spine4.tx")`;
float $findMEY = `getAttr("j_spine4.ty")`;
float $findMEZ = `getAttr("j_spine4.tz")`;
float $findRX = `getAttr("j_spine4.jointOrientX")`;
float $findRY = `getAttr("j_spine4.jointOrientY")`;
float $findRZ = `getAttr("j_spine4.jointOrientZ")`;

// Stage 2: Setup transforms

select -r helmet_bound:j_spine4;
setAttr "helmet_bound:j_spine4.translateX" $findMEX;
setAttr "helmet_bound:j_spine4.translateY" $findMEY;
setAttr "helmet_bound:j_spine4.translateZ" $findMEZ;
setAttr "helmet_bound:j_spine4.jointOrientX" $findRX;
setAttr "helmet_bound:j_spine4.jointOrientY" $findRY;
setAttr "helmet_bound:j_spine4.jointOrientZ" $findRZ;

// Stage 3: Cleanup

delete j_neck;

// Stage 4: Done

print "Done On to Manual Step!";
```

> **WARNING:** If you are using a model set with no arms on the body, you may have to manually rename `helmet_bound:j_spine4` back to just `j_spine4`

*Final step: Binding the finished body properly*
- Find the `j_spine4` from the body mesh.
- Expand it and select all it's children.
- Middle mouse drag the children onto the `helmet_bound:j_spine4`
- Delete the `j_spine4` from the body.
- Drag on the body's bind file.
- Save the scene, the head is now properly attached to the body.
