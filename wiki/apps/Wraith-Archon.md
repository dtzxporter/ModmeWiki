1.  Wraith Archon - The Call of Duty Asset Extractor {icon cog spin}
Extracts various assets from the !!Call of Duty!! games
1.  [[>> Download <<|http://aviacreations.com/wraith/]]

1.  Usage
Using Wraith Archon is simple, simply find the asset type you want to extract below, and either load the game, or open the file directly with Wraith Archon. When the game is running, clicking !!Load Game!! will load all the available assets that are currently available. !!Load File!! or drag and dropping a file will allow Wraith Archon, if supported, to load the assets in the package. (See table below for more information)

1.  Smart search
Wraith Archon has a smart search feature. Using commas, you can search for multiple keywords in the loaded assets. If your search query starts with an ! it will !!exclude!! (blacklist) what you put in the search box, the opposite of search.

// Find all viewmodels and npc models
vm_,npc_
// Don't show me npc or vehicle models
!npc_,veh_


NOTE: When looking for assets, a lot of times the asset names aren't exactly what you'd expect. Wraith Archon does however, load all the assets currently available in the respected map or lobby you have loaded. If you can't find it, it has a different name. In addition, level assets can sometimes be merged directly into the map if it's a static model.

1.  Game support information



| Game | XModels | XAnims | XImages | XEffects | Raw Files | Sounds
| ----- | ----- | ----- |  ----- |  ----- | ----- | -----
| World at War | In-Game | In-Game | IWD Files | No | No | No
| Black Ops 1 | In-Game | In-Game | IWD Files | In-Game | No | No
| Black Ops 2 | In-Game | In-Game | IPAK Files | In-Game | In-Game | SAB Files (S/L)
| Black Ops 3 | In-Game | In-Game | XPAK Files (S) / In-Game (L) | In-Game | In-Game | SAB Files (S/L) 
| Black Ops 4 | In-Game | In-Game | XPAK Files (S) / In-Game (L) | No | In-Game | SAB Files (S/L) 
| Modern Warfare | In-Game | In-Game | IWD Files | No | No | No
| Modern Warfare 2 | In-Game | In-Game | IWD Files | No | No | No
| Modern Warfare 3 | In-Game | In-Game | IWD Files | No | No | No
| Ghosts | In-Game | In-Game | In-Game (S) | No | No | No
| Advanced Warfare | In-Game | In-Game | In-Game (S) | No | No | No
| Infinite Warfare | In-Game | In-Game | In-Game (S) | No | No | SAB Files (S/L)
| Modern Warfare Remastered | In-Game | In-Game | In-Game (S) | No | No | No
| World War II | In-Game | In-Game | In-Game (S) | No | No | In-Game (S/L)

Key:
- S / L = Streamed and Loaded, some assets are streamed from the disk, some are always loaded.
- In-Game means that you have the general setting checked off for the asset type
- File type exporting is just opening the file via !!Load File!! or !!drag and drop!!.

> Some games use placeholders heavily, where certain weapons and models may not be loaded until they are in the players hands and sometimes 3rd person models aren't loaded unless you're in-game with someone else.

NOTE: You can use the lobby preview feature (Hovering over a locked item) to get the model to load in some cases for items and content you don't have.

NOTE: Some SAB files may have pairs of entries (One in a SABL, one in SABS) the entry in the SABL file may be cut-off, this is normal, you must find the corresponding SABS entry for the full audio

NOTE: Black Ops 4 currently uses the CASC filesystem. You must rebuild the files from it in order for Wraith to properly read them. The files should be placed in <Black Ops 4 Root>\zone. To load XPAK files once extracted, you must have previously use the 'Load Game' setting on Black Ops 4 for proper extraction

Still need help? Visit the forums: [[Forums|http://aviacreations.com/modme]]