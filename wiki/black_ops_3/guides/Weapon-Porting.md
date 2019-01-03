# Weapon Porting

### Introduction & Prerequisites
Porting a weapon into Black Ops 3 is slightly different from porting a weapon into older games such as Call of Duty 4, Call of Duty 5 or Black Ops 1, and requires several extra steps to get everything set up.  
- **Required programs: [Wraith](http://aviacreations.com/modme/index.php?view=topic&tid=69), [Kronos](http://aviacreations.com/modme/index.php?view=topic&tid=179), [Autodesk Maya](http://www.autodesk.com/products/maya/overview), [CoDMayaTools 2.0](http://aviacreations.com/modme/index.php?view=topic&tid=87), [Black Ops 3](http://store.steampowered.com/app/311210/), [Black Ops 3 Mod Tools](http://steamcommunity.com/app/455130)** 
- **Required knowledge: Mod tools overview, basic Maya knowledge**

The basic workflow of getting a custom weapon into Black Ops 3 is as follows:
 - Obtaining the model  
 - Preparing the model  
 - Exporting the model  
 - Compiling the model in APE  
 - Compiling materials for model
 - Converting animations from older games
 - Compiling animations in APE
 - Creating the weapon file
 - Adding weapon to a map in Radiant

Although this process might appear daunting at first, often taking first-timers up to 4 hours to complete a single weapon port, you will figure out your own shortcuts along the way to speed up the process. Any `TIP`s or `WARNING`s that you see are things I have noted to have worked/not worked based on past experiences. Try to adhere to these and see if they work for you.

## Obtaining the model
Use Wraith to rip models from BO3, BO2 or BO1, MW, MW2 and MW3 - Ensure you rip every model you wish to use for the weapon (e.g. snipers have the body, scope and magazine as separate models).

Open Wraith and log into your Modme account. You will only need to do this once.

Click on Settings and under Models, ensure that `Export .MA` and `Export .XMODEL_EXPORT` are checked. The other two are optional, but are not needed for this process. 

Select the game you wish to rip from in the top-left dropdown menu.

{F74}

> **NOTE:** Open the game you are ripping from BEFORE touching any other options within Wraith.

Start a custom game so that the game begins to load the assets into memory.

Click 'Load Game' in Wraith and wait for the asset list to fill.

Once the assets have finished enumerating, enter a search term to filter down the number of assets listed.  

> **WARNING:** Not all assets are named the same as the in-game weapon name (e.g. Kuda = ap9; ICR-1 = irs27). Experiment with models and try to find the one you are after.

Highlight all assets you wish to export and click the Export Selection button in the top-right. Wait for the success toast message to appear.

## Preparing the models
> **NOTE:** **If you do not wish to edit the models before compiling them, skip to Step 3.**

Open the .ma file for the models you exported. Change the Renderer to 'Legacy Default Viewport' and press 6 to go into textured view.

{F80}

{F82}

> **WARNING:** Ensure you go `File > Open` and locate the .ma file rather than dragging-and-dropping the .ma file into your scene. Dragging-and-dropping the file will merge it with the untitled scene and add a namespace in front of all your imported items, which may lead to issues later down the line.

Drag the bind .mel file into the Maya window and wait for the status bar at the bottom to say 'The model has been binded.' Do this for every model that you ripped, saving the changes as you go.

{F84}

Open the 'main' model that the weapon will use. This will generally be the body piece that has the trigger and pistol grips, then click `File > Import` and import each of the other models you ripped into the same scene. Try to take note of which joints are associated with which models during this process.

{F86}

> **NOTE:** You may drag-and-drop the other model files for this step, as both methods will lead to the same result.

Attach all imported joints to the root joint of the main model (normally j_gun or tag_weapon) by hovering over the joint to move, holding middle mouse and then dragging it to the root bone of the main model.  [Example](https://u.pomf.is/cdjqpv.mp4).

Click on the joints attached to each of the imported models (usually identifiable by the namespace at the beginning of the joint name: e.g. `t6_attach_mag_dsr50_view_LOD0:tag_clip`) and use the Move and Rotate tools to align it to where you feel is correct. 

{F88}

> **NOTE:** Save this as a new scene somewhere easy to access, this will be used for creating the animated model when converting animations.

## Exporting the model

Click on **Call of Duty Tools** in the Maya toolbar and select **Export XModel**.

Highlight all the nodes in Outliner (`Window > Outliner` if you cannot see it), then click `Select > Hierarchy` or `Edit > Select Hierarchy`, depending on your Maya version.

Click the slot dropdown and select Slot 1, then click !!Save Selection! in the Export XModel window. Now click the three dots to navigate to a path first, then enter the name of your xmodel_export.

{F90}

Click **Export Selected** and respond to the save prompt however you wish, then wait for the progress bar to finish.

Open Kronos and click on the `Model and Animation Converter` tab (the cube):

{F92}

Drag and drop all your .xmodel_exports into Kronos and wait for another window to appear with your converted XMODEL_BIN files. Copy these and place them into your `%BO3Dir%/model_export` folder (you may place them in any subdirectory inside the model_export folder).

While you have Kronos open, find all the textures exported by Wraith and drop them into Kronos' image converter to convert them to .TIFF, the only image format Black Ops 3 supports.

## Compiling the model in APE
Access APE by launching the Black Ops 3 Mod Tools on Steam, then clicking the monkey button in the toolbar:

{F95}

Create a new .GDT for your weapon by clicking the new GDT icon or pressing `Ctrl+Shift+N`. Name it something relevant to the weapon you are porting so you can keep assets organised.

{F97}

> **NOTE:** After making your GDT, you can quickly find it by typing the name of the GDT into the GDTs field in the Filters section

Right click on the GDT entry or press `Ctrl+N` to create a new asset. Name it however you wish, but ensure the !!Asset Type!! is set to !!xmodel!! and the GDT is set to the GDT you just made. 

{F99}

> **NOTE:** For consistencies sake, try to name your assets in a standardized fashion. As a template, Treyarch use `<game_id>_<model_usage>_<weapon_class>_<weapon_name>_<model type>`. e.g. `t5_wpn_sniper_l96a1_view, t6_attach_mag_dsr50_view`, `t6_attach_mag_dsr50_view`.

Set the model type to **animated** and specify the XMODEL_BIN file you just exported under LOD0, then change **BulletCollisionLOD** to **LOD0**.

{F101}

Scoll down to the submodels section and add any additional models your weapon requires into the **Model** field. Always use the parent bone of your main model as the **Parent tag** (e.g. tag_weapon).  

> **NOTE:** If you cannot see the Preview window already, go to `View > Toolbars > Preview` and enable it. Then click on the titlebar where it says Preview to pull it into its own window.

Tweak the offset and angles for the submodel until it sits where it should. Remember these values and remove the model in the !!Model!! field so the submodel is no longer attached to the main model.

## Compiling materials for model

Scroll down the xmodel details slightly to reveal the materials list. Click on the name of the material to create a new instance of a material with the correct name.

In the material settings, set `Material Category` to `Geometry`, `Material Type` to `lit_weapon` and `Surface Type` to `<none>`. You may experiment with these, but these are the recommended settings for normal weapon textures.  

Tip: To speed up the process, create a material with these parameters changed, and then right click on it and click Duplicate and rename it to the names of every other material you need to create.

> **NOTE:** As Black Ops 3 uses a PBR system, the required textures are: diffuse/albedo, ambient occlusion, normal, specular and gloss. When coming from an older Call of Duty game, the colour map (texture suffix _c) can be used in the diffuse channel, and the environment map (suffix _e or _env) can be used in the gloss channel.

Click the small 'new image' icon next to the field for each texture map, which will create an image asset in the GDT for you to specify your texture location. Find all your corresponding textures for the image assets and the material will be updated automatically.

{F103}

Repeat for each material your model requires.

## Converting animations from older games

Converting animations from older games is easy thanks to the rig I created, download it here: [HERE](http://aviacreations.com/modme/index.php?view=topic&tid=1375)

First `bind and align` any attachments if necessary.

Open `conversion_rig.ma` and import your gun. Ensure that, at this stage, the root bone of the weapon is `NOT tag_weapon`.

Make the `root bone` of your gun (`e.g. j_gun`) a child bone of `t7:tag_weapon_right` and `zero out the transforms`. (Middle mouse click and drag the joint onto the root)

Click on `t7:Joints` and click on `Select > Hierarchy`, then execute the `renameRig.mel` script. All joints under `t7:Joints` should now have the `_t7 suffix`. (Verify it yourself! Don't rush)

Import an animation file like normal, (Drag and drop)

Click on `t7:Joints` and click on `Select > Hierarchy`, then execute the `removeNamespace.mel` script. All joints under `t7:Joints` should no longer have the `_t7 suffix`.

Rename the `root bone` of your gun (`e.g. j_gun`) to `tag_weapon` in the viewmodel.

Select `t7:tag_torso` and `t7:tag_cambone`, then click on `Select > Hierarchy` and export as normal.

You may open the .xanim_export file in a text editor to confirm that the _t7 suffixes are absent. If they are still in the file, or you forgot to complete Step 6, you may replace all '_t7' strings with nothing.

_For ADS animations only_: Treyarch animations, export ONLY `t7:tag_view` and `t7:tag_torso`. For IW animations, export ONLY `t7:tag_view` and `t7:tag_ads`.

> **Q:** Why do the anims sometimes not fit the gun properly?
**A:** Due to Treyarch changing the bone structure significantly, getting a 1:1 match in bone positioning was impossible to achieve. In addition, the rig uses Jessica's viewarms from Shadows of Evil simply due to her hands being the thinnest in the game. This will ensure that the anims will fit on all hands, despite being thicker than Jessica's hands.

## Compiling animations in APE
Create an xanim asset in your GDT by right-clicking on the GDT name and selecting New asset, then changing the Asset type to xanim.

Select your XANIM_BIN file for the Anim file field, and the animated model you exported for the Model file field.

**Deselect Use Bones** and set `Type` to `relative`. For animations that should loop (idle, sprint_loop, slide_loop, swim animations), check the **Looping** box.

Do Steps 1-3 for each animation your weapon requires  

> **Tip:** Similarly to the material creation process, you can set up the animation parameters for one animation asset, then duplicate it while changing the name so you do not have to change each asset's parameters individually.

## Creating the weapon file
Right click on your GDT's name and add a `new asset` with the type `bulletweapon`.

Open the official weaponfile for your weapon (e.g. l96a1_mp from Black Ops 1) in a text editor and copy the values over to APE.

Under the `XModels` group, add your viewmodel and world models to the fields. They will only display valid xmodels in your GDT database.

Scroll down slightly and add the default scope for your weapon (if applicable) to Optic 1 and attach it to `tag_weapon`, then modify the View Offset Position and Rotation values to what you entered into the main xmodel's submodel offsets.

Scroll down to the `XAnims` section and add all your animations to these fields. As you type, APE will filter down all the xanim assets available in your GDT database.

Use the following properties descriptions to help setup the weapon file:

<table>
      <tr>
          <td>Display Name</td>
          <td>Localization alias (name) for weapon name displayed on HUD in game.</td>
      </tr>
      <tr>
          <td>In-Game Name</td>
          <td>Actual in-game weapon name.</td>
      </tr>
      <tr>
          <td>Player Anim Type</td>
          <td>Specify the world animation to play when holding the weapon.</td>
      </tr>
      <tr>
          <td>Type</td>
          <td>The type of weapon to use.</td>
      </tr>
      <tr>
          <td>Impact Type</td>
          <td>The impact type, used to play impact effects based on surfacetype.</td>
      </tr>
      <tr>
          <td>Fire Type</td>
          <td>Behavior of the weapon when the trigger is held down.</td>
      </tr>
      <tr>
          <td>Burst Count (For burst effect)</td>
          <td>Specifies how many bullets shot by either regular or auto burst fire.</td>
      </tr>
      <tr>
          <td>Reload Options [Big property page]</td>
          <td>Specify the reload properties, example: Thundergun would be no partial reload.</td>
      </tr>
      <tr>
          <td>Ammo Name</td>
          <td>Allows different weapons to share the same ammo pool.</td>
      </tr>
      <tr>
          <td>Clip Size</td>
          <td>Specifies how many bullets per clip/magazine.</td>
      </tr>
      <tr>
          <td>Start Ammo</td>
          <td>How much ammo the player gets when starting with this weapon. One clip/magazine from this amount will be already in the weapon. No effect on AI.  Affected by `Ammo Clip Count Relative` field.</td>
      </tr>
      <tr>
          <td>Damage Ranges [Big property page]</td>
          <td>The damage done to enemies on various parts of the body.</td>
      </tr>
      <tr>
          <td>State Timers [Big property page]</td>
          <td>Verious timers related to animations, and weapon stats.</td>
      </tr>
      <tr>
          <td>View Gun</td>
          <td>The XMODEL to display in the first person view.</td>
      </tr>
      <tr>
          <td>World Gun</td>
          <td>The XMODEL to display in Co-op and 3rd person.</td>
      </tr>
      <tr>
          <td>XAnims [Big property page]</td>
          <td>Specify you're already ported XANIMS to play during the event listed on the left of APE.</td>
      </tr>
</table>

## Adding weapon to a map in Radiant
Adding your weapon to the map is easy, simply go to the `entity browser` and expand the `weapons` section. You'll be able to **drag and drop** your weapon from there.

## Compiling the map for testing
In the launcher, right click on the map you have added the weapon to and click `Edit Zone File`. You can open it using any text editor. Add the line `weapon,WEAPONNAME` at the bottom of the zone file, replacing WEAPONNAME with the name of the weapon asset you created in APE. e.g. weapon,l96a1_mp.

Tick the map name in the list, then tick Compile (Full), Link and Run, then click Build.

If there are no errors, the game will open and load into your map. The weapon should be on the floor where you placed it in Radiant.

## Congratulations! You have successfully ported your weapon into Black Ops 3!

---

_Contributors:_
- Azsry (If this tutorial helped you out at all and you wish do donate you can here [Paypal](azsry@live.com.au))