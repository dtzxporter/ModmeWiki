(NOTE) It is advised that you take your time while following these instructions.

1. Export the models (.ma) and anims (.seanim). Please do not export MEL scripts for the anims as some are currently broken.

2. Drag the bind script onto your models in the .ma scene for each hand's _viewmodel (_lh, _rh) and for the _world models. Save the scene.

3. Rename the _lh weapon:


    j_gun1 --> tag_weapon_le
    tag_brass1 --> tag_brass_le
    tag_flash1 --> tag_flash_le

4. Export the _lh weapon but **do not** save the scene.

5. Rename the _rh weapon:


j_gun --> tag_weapon


6. Export the _rh weapon but **do not** save the scene.

7. Open up Azsry's conversion rig (make sure to use the latest version). [[Click here to download it.|https://mega.nz/#!8QkUwA5Q!cJeE1zxPrRs70hbamlyiWF5o4hMlRjddavG9fm6zIPY]]

8. File > Import, and choose the type as a maya scene then select your _lh version of the gun and improt it. Do the same with the _rh version.

9. Locate your _lh version's joints and select hierarchy on them. Import the remove namespace script. Do the same with _rh version.

10. Find j_gun and drag it under tag_weapon_right in t7:joints.

11. Find j_gun1 and drag it under tag_weapon_left in t7:joints.

(IMPORTANT) Make sure you **do not** rename j_gun and j_gun1 as it will mess with the import process of the seanims.

12. Save-as and place it somewhere you'll remember.

13. Go to `File > Recent files` and re-open the rig to make it much quicker when importing anims. (Bottom of menu).

14. You'll now want to export your anim model. Exactly the same was as normal, tag_view (h) and select at least one mesh from the t7 rig then export xmodel.

15. Now import your first seanim. Most should be named in the convention of _. (e.g. dw_lh_idle).

16. Export the following for each anim accordingly:

ADS Anims: tag_view, tag_torso
FULL Anims: tag_torso (h), tag_cambone (h)
Left Hand Anims: j_shoulder_le (h), tag_weapon_left (h), tag_cambone(h), tag_torso
Right Hand Anims: j_shoulder_ri (h), tag_weapon_right (h), tag_cambone(h), tag_torso
(h) = select hierarchy

17. If your weapon has an idle loop that has a substantial amount of frames (e.g. 300), then import the idle anim for each hand into the rig so both guns can be seen in the idle position. Then export using the FULL Anims method. And only export the first 2 frames. Or 2 frames that do not change position. These will be used for sliding.

18. In each xanim_export file that you exported, you must rename the following like before.

Right & Full Anims:
      j_gun --> tag_weapon
Left & Full Anims:
      j_gun1 --> tag_weapon_le
      tag_brass1 --> tag_brass_le
      tag_flash1 --> tag_flash_le

19. Once done, save. Then export2bin * (Drag and drop onto kronos)

20. Import all of the anims into APE like normal. Not forgetting to export2bin (Or kronos) on all of your models too.

You can use my GDT provided as a reference for your weapons. [[Click here to download the files.|https://mega.nz/#!OAU1SAiJ!SkTC8Q-MfZC3bof5TPDrXJQz2jR24ZCwbcnDHeMhHzw]] 

NOTE: This isn't a drag and drop zip, it only has reference files for your viewing. If not just use one from the BO1 Mod Tools (BETA) or WaW. They are in fact compatible with the current mod tools.

21. Make sure in your lh weapon file in APE has Inventory set to: dwlefthand.

22. Once everything is ready. Add both lh and rh variants to your zone file and link then run and you're good to go! 

--- 

//**Credits:**//
[[KommunityKOD|https://www.youtube.com/user/KommunityKOD]]
JBird632
Azsry