# Vega - The Doom Eternal Asset Extractor
Extracts various assets from the game "Doom Eternal". This software was developed by [DTZxPorter](https://twitter.com/dtzxporter) & id-daemon.

## ⬇️ Download and version info:

> **IMPORTANT:** By downloading this software you are agreeing to the **EULA** located in the `About` tab of the program.

- Download (Windows x64): [Vega (v2.00)](https://mega.nz/file/IZhFCC6b#-GgCHmUoyaBCGJb64qVGyObg1Hu-N5gfsBqhEBdm5AU).
- Download (Linux x64): [Vega (v2.00)](https://mega.nz/file/EYYRjDra#nQPNUGtuCCVXQSehzAn_EEvFGJiqivdxtDx4sYoLrUc).
- Download (macOS ARM): [Vega (v2.00)](https://mega.nz/file/lI4HhZjb#AbFCX_Ia_I4Hd2uStRwvSN4l1vpnPhqtUQPw3BBbl-Y).

## ❤️ Donate:
- I take time out of my day to make this happen.
- Show your support: [HERE](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=686S5QL7Z4HKQ)

## ⚙️ Usage:
Using Vega is fairly simple as the tool only requires the files located within "base" in order to function.

- The tool features a user interface, just open up a resource file using `Load File`

> **IMPORTANT:** Both the tool and the game **require** the entirety of the base folder to be intact and must not be modified in any way.

## Ripping:
- The **.resource** files contain various encoded assets that Vega can export; and, as of now the currently supported assets are:
  - Textures as [Dds, Png, Tiff]
  - Models as [SEModel, OBJ, XNALara, SMD, CoD XModel, Maya, Kaydara FBX, Cast].
  - Animations as [SEAnim, Cast].

> **NOTICE:** You should select all `_patchX` .resource files in order to export assets properly. Order doesn't matter.

## 📌 Versioning:
- 1.00 - Initial Release (BETA).
- 1.01 - Fixed FBX/XNALara files. Fix for some skinned models not exporting. `gameresources.resources` is now loaded REGARDLESS of the package you select.
- 1.10 - Animation export support.
- 1.11 - Fixed crash on export of some assets.
- 1.20 - Better support for static models. Added support for UV Layer 2 (Only supported in SEModel/Cast Models) for static models.
- 1.30 - Fixed various export crashes with DLC aassets, Add support for previewing textured mode (ColorMap only).
- 2.00 - Completely rewritten, cross platform. Fixes for various models, animations, textures failing to export, better FBX support, and more.