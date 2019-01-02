(NOTE) Black Ops 3 modtools use the TIFF image format. Most image editors include this format (Paint.net, Photoshop, Gimp all include it for example). If yours doesn't, find a plugin for it, or use one of the aforementioned image editors. [Kronos](http://aviacreations.com/modme/forum/topic.php?tid=179) also has a built-in image converter which converts most formats, including IWI (from previous CoD games), to TIFF.

  *Create file**

If you don't already have a custom GDT, make one with "New GDT" in APE. I've named mine `custom_t7`. (This is because Treyarch's updates to the tools can overwrite any changes you make to the GDTs already provided.)

IMPORTANT: Always save your GDT files in `Black Ops 3\source_data` or it won't show up in APE or Radiant next time you open it.

Click `New Asset` next to the GDT button. Give it a name, select type `material`, then your custom GDT if it isn't already selected. I've called mine `mtl_tutorial` and used this image:

{F52}

NOTE: The image dimensions must be in a power of 2.

  *Material Settings**

 - Give your material the appropriate settings for the texture you're making. Almost all common materials will use the material type `lit`. Here are my settings:

{F54}

<table>
      <tr>
          <td>Material Category</td>
          <td>The material will have certain options and settings based on its category. Most materials will just have `Geometry`. Weapon materials go under `Weapons`.</td>
      </tr>
      <tr>
          <td>Material Type</td>
          <td>Similar to above, types will have certain options available specific to them for their respective contexts. Almost all common materials will have the type `lit`.</td>
      </tr>
      <tr>
          <td>Surface Type</td>
          <td>In-game mechanics, like sound (e.g. footsteps), need to know how to interact with materials. This is where you define that. Do not leave it as `error`. `none` is used when you don't want materials to interact with anything.</td>
      </tr>
      <tr>
          <td>Gloss Range</td>
          <td>Different gloss ranges will make the texture shine/reflect in different intensities in-game. Selecting `custom` means you can define specific values under the Specular and Gloss section. `full` means full gloss.</td>
      </tr>
      <tr>
          <td>Usage</td>
          <td>Which category the material will be sorted under in Radiant, if any.</td>
      </tr>
</table>

You can ignore the Asset Tags, Enemy Material and FrameBuffer Operations sections for almost everything.

  *Color map, normal map, etc.**
The color map is the actual color texture you want. Click this button to add a new image to your material:

{F56}

Click the three dots next to the Texture box and a dialog will pop up. Select the image you want to use. You probably don't need to tweak any settings, but do so if you need to.
Repeat this for the normal map. You can quickly generate normal maps for your images at: [NormalMap-Online](https://cpetry.github.io/NormalMap-Online/).

  *Save and use**

Click  `Save All`. 

In Radiant, in the Texture Browser, look for the material name (i.e. mine was mtl_tutorial), and apply it to brushes as normal.

{F58}

(NOTE) More advanced information on specific material types can be found in the provided documentation in `bo3\docs_modtools`.

--- 

//**Contributors:**//
Koan
DTZxPorter