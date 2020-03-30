# Vega - The Doom Eternal Asset Extractor
Extracts various assets from the game "Doom Eternal". This software is considered **Work-in-Progress** developed by [DTZxPorter](https://twitter.com/dtzxporter) & id-daemon.

_Download and version info:_

> **IMPORTANT:** By downloading this software you are agreeing to the **EULA** located inside of the archive (EULA.txt).

- Download Link: [Vega (v1.11 BETA)](https://mega.nz/#!cRZRDIib!uXCu_jlUqkrkbFtSuRMU68C4MXmA3kMKln5xDucuDP0).
- Requires Visual Studio 2019 x64 Redist: [Redist](https://aka.ms/vs/16/release/vc_redist.x64.exe).

## ❤️ Donate:
- I take time out of my day to make this happen.
- Show your support: [HERE](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=686S5QL7Z4HKQ)

> **NOTICE:** The tool is in BETA, some static models need to be fixed. Animations are coming soon.

## ⚙️ Usage:
Using Vega is fairly simple as the tool only requires the files located within "base" in order to function.

- The tool features a user interface, just open up a resource file using `Load File`

> **IMPORTANT:** Both the tool and the game **require** the entirety of the base folder to be intact and must not be modified in any way.

## Ripping:
- The **.resource** files contain various encoded assets that Legion can export; and, as of now the currently supported assets are:
  - Textures as [Dds, Png, Tiff]
  - Models as [SEModel, OBJ, XNALara, SMD, CoD XModel, Maya (Legacy), Kaydara FBX, Cast].
  - Animations as [SEAnim, Cast] (Coming soon).
  
## ⚠️ Notice:
- SE* formats (SEModel, SEAnim are preferred over any other export format and have guaranteed compatibility).

## 🖥️ Desktop Wallpaper:
- Coming Soon.

## 📌 Versioning:
- 1.00 - Initial Release (BETA).
- 1.01 - Fixed FBX/XNALara files. Fix for some skinned models not exporting. `gameresources.resources` is now loaded REGARDLESS of the package you select.
- 1.10 - Animation export support.
- 1.11 - Fixed crash on export of some assets.