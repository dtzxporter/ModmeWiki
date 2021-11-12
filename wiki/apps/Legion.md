# Legion - The Apex Legends Asset Extractor
<img src="{{ 'LegionBanner.jpg' | relative_link}}" alt="drawing" style="height: 255px; display:block;margin-bottom: 12px;"/>
Extracts various assets from the game "Apex Legends". This software is developed by [DTZxPorter](https://twitter.com/dtzxporter) & id-daemon.

## ❤️ Donate:
- I take time out of my day to make this happen.
- Show your support: [HERE](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=686S5QL7Z4HKQ)

## 💾 Download and version info:

> **IMPORTANT:** By downloading this software you are agreeing to the **EULA** located inside of the archive (EULA.txt).

- Download Link: [Legion (v2.36)](https://mega.nz/file/ZYwXVYyT#wSdVPa1BnRj3eI83D-WxMP-Mu38AvHCmw5YCeyR6Sq0).
- Download Link (TF2 Supported) *NOT FOR APEX*: [Legion Legacy (v2.13)](https://mega.nz/file/4NJSyQyA#4B-XEiAOujpWsECRHsxHwT9PzL_OUY8X9Rf56JA2KYA)
- Requires Visual Studio 2022 x64 Redist: [Redist](https://aka.ms/vs/17/release/VC_redist.x64.exe).
- Currently works as of 11/6/2021 updates.

## ⚙️ Usage:
Using Legion is fairly simple as the tool only requires the files located within "Apex\paks\Win64" in order to function.

- The tool features a user interface, just open up an MBnk or RPak to extract assets using `Load File`.

> **IMPORTANT:** Both the tool and the game **require** the entirety of the Win64 folder to be intact and must not be modified in any way.

## Ripping:
- The **.rpak** files contain various encoded assets that Legion can export; and, as of now the currently supported assets are:
  - Textures as [Dds, Png, Tiff]
  - Models as [SEModel, OBJ, XNALara, SMD, CoD XModel, Maya (Legacy), Kaydara FBX, Cast].
  - Animations as [SEAnim, Cast].
- The **.mbnk** file contains all the audio for the game:
  - Sounds as [Wav].
  
## ⚠️ Notice:
- SE* formats (SEModel, SEAnim are preferred over any other export format and have guaranteed compatibility).
- Legion is considered *feature* complete, and will only receive updates that improve compatibility with new seasons.

## 🖥️ Desktop Wallpaper:
- A slick wallpaper for Legion (By @Spooky_Sal): [Download](https://mega.nz/#!1dh2yaBY!krhTFxou3eYwrl98XVnS40fvUS69wVMVm4pLd8Oo-GM)
- An electrifying poster for Legion S2 (By @Spooky_Sal): [Download](https://mega.nz/#!ABBGkKza!0L_YWs-T6TGMcEBnBvk9UqMaVhxvN5oUatIGAPN8KY8)
- An eerie for Legion S4 (By @Spooky_Sal): [Download](https://mega.nz/#!cQ5AAAIb!9p-6J-2Sdjm6TuBCc9VBY53SzoWpqco1eu0Is5lysWQ)

## 📌 Versioning:
- 0.18 - Initial Release.
- 0.54 - Model export support, fixed patch_master crash, skip existing images.
- 0.60 - Patch rpak support, xmodel_export model format.
- 0.61 - Shadow fix for mp_rr* crash...
- 0.62 - Fixed SMD export when invalid normals exist, fixed materials in xmodel_export.
- 0.68 - Fixed season 1 rpak patches causing crashes.
- 0.84 - Initial support for animations, performance tweaks, maya (legacy) exporter.
- 0.95 - Image format toggle (Dds, Png, Tiff), fixed rare image bug having wrong size.
- 0.98 - Added support for my new FBX exporter.
- 1.00 - Support for Apex S2, support for new multi-UVs, support for last few missing image formats (Requires S2 files).
- 1.01 - Fix for large scale map models which were broken on export.
- 1.02 - Fix for crash on some smaller paks.
- 2.00 - Support for most patched assets, new user interface with built-in model previewer. Material/Skin export ability and new Image format, compatible with S4.
- 2.10 - Support for Titanfall 2 (Models, Animations, RPaks, Sounds). Preliminary support for the new Cast format. Image preview (press p). Apex animation fixes. FBX export tweaks for UV Layers.
- 2.11 - Fixed crash in some TF2 Rpaks, fixed bug with some TF2 models missing animations.
- 2.12 - Export all material slots, fixed FBX and XNALara exports with skeletons.
- 2.13 - Fixed crash introduced in v2.12 when additional material slots were added.
- 2.20 - Support for Apex S7 (Not backwards compatible)
- 2.21 - Fixed crash during model exports, fixed animations missing parts. Added support for previewing w/ materials. Fixed bug with some image formats.
- 2.22 - Support for Apex S8 (Audio is no longer backwards compatible), Fix for crash involving an unsupported model format in other paks.
- 2.23 - Add support for missing scales in animations. (Only tested in Maya, may not function properly in Blender)
- 2.24 - Fixed crash on some models after the chaos update, PNGs have improved compatibility with legacy style importers.
- 2.3 - Support for S11's UI Image asset, Textures in BC6 format, custom export directory paths.
- 2.31 - Fixed a rare crash that would happen when previewing certain models. Added S11 splash screen.
- 2.32 - Fixed certain resolution UI Image's from exporting incorrectly. Fix crash with custom export folders. Add support for embedded 'starpak' data (store rpak files).
- 2.33 - Fixed crash on models that have blank or empty submeshes. Update to Visual Studio 2022 (Requires new runtime).
- 2.34 - Fixed vertex weights on some models that had invalid data.
- 2.35 - Fixed issue with vertex weights on some models after (2.34). Generate database linking animations with no animrig to their original models (bird, etc). These export _with_ the model now. Materials can be previewed by viewing the albedo map.
- 2.36 - Fixed weighting issues (again). Should now export all models weighted properly.