Water in !!Call of Duty: Black Ops 3!! is composed of 3 different parts. Depending on how you'll be using your water, you might not need all 3 parts.

  * Water Texture
  * Clip Water
  * PBG Box

1.  Water Texture
Primarily, and most importantly all water needs an actual texture. These textures can easily be found by going to usage in the !!Texture Browser(T)!! and selecting !!Water!!.
IMPORTANT: Water textures won't render unless //Realtime Rendering// is enabled.

---
1.  Clip Water
While a water texture will do the visual aspect of rendering water for you, !!clip_water!! will allow it to act like proper water. Allow players to swim in it, or walk slower depending on how submerged they are & proper effects upon impact. Create a brush & apply the !!water_clip!! texture to it, and have it cover your desired area.

---
1.  PBG Box
Finally, a PBG Box, found in the !!Entity Browser(B)!! will allow you to discolour the view of players inside the selected area. Much like a reflection probe, place the PBG Box and resize it to your liking. Then it's time to edit it's KVP's. As a start, you'll want to:
  * Enable !!USE_UNDERWATER!!
  * Edit the KVP's !!underwater_absorbtion!! & !!underwater_mix!!.
Of course, you can mess around with more KVP's to see what fits your liking the most.

---
//**Contributors:**//
Exofile