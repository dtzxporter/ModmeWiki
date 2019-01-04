# Wraith Cyborg - The Call of Duty ONLINE Asset Extractor
Extracts various assets from the `CODOL` game

> **IMPORTANT:** Wraith Cyborg will NOT be receiving updates like Wraith Archon. If you want something, rip EVERYTHING now.

_Download and version info:_
- Download (Agreeing to the [EULA](http://aviacreations.com/wraith/): [Wraith Cyborg (v1.0.6)](https://mega.nz/#!BUgDWaZB!CYzhqTcOhaEpan4xs8cxbkOBAUsOASuX73ugQVF4al0)
- Game version: 3.10.23.2 (Exe version, **differs from site**...)
- Game SHA1: "bdf7d6fa9005539cfb962d82eed3a8c042828728"

## Usage:
Using Wraith Cyborg is complex, due to the nature of the game. You MUST follow the instructions exactly as stated or you will have a hard time getting it working. In addition, **I will not** be providing support for it, you're on your own.

> **WARNING:** Wraith Cyborg will only function on a fully downloaded copy of the game.

- Step 1: *Clean Slate* will be used in this tutorial several times. If you see it, that means reset back to Step 1 (This is a requirement).
- Step 2a: Close all running programs, including 'WeGame' 'TenProtect' and the game itself. (They are in the taskbar icons, to the right).
 - Step 2b: If you are unable to do so, it's probably best to **restart your computer**.
- Step 3: Run Wraith Cyborg as admin, this is a requirement due to the game, in addition, you should **add an exception now** to your anti-virus, because Wraith Cyborg requires high-level access to be able to work on the game.
- Step 4: Wraith will be using a lot of CPU during this phase, so launch the game now from the launcher.
- Step 5: Once Wraith finds the game, it will either print "**Permissions Granted**" or "**Failed to attach**". If you get Failed to attach, hop back to *Clean Slate*. Otherwise continue to the Ripping segment.

## Ripping:
- To rip from the game, you can use one of four commands:
 - "ripanims" Will rip all loaded XAnims, you can change the format to xanims with "ripanims xanimwaw or xanimbo".
 - "ripmodels" Will rip all loaded XModels, at the current resolution settings (Play HQ for better models) you can change the format with "ripmodels obj" and change the image format with "ripmodels ma dds".
 - "ripsounds" Will rip all loaded Sounds.
 - "ripimages" Will rip all loaded XImages, you can change the format to dds with "ripimages dds".
- To rip an IFS file, you can just drag it onto the application, it will extract images and audio files.
 - You can run with "WraithCyborg.exe <ifsfile> dds" to convert to a DDS instead of a PNG

> **NOTE:** Wraith can only rip loaded models, in addition, you should play at the HIGHEST graphical settings you can run at, to get the best quality. Also, you can't run ripping commands while levels are loading / changing. Wait until it's loaded. (Guns can be ripped from CAC)

> **NOTE:** Some audio in COD:OL can't be used directly and must be converted, you can use ffmpeg -i input.wav output.wav to convert it.

## Versioning:
- Only export models if they don't exist (For speed)
- Exporting of custom XAUDIO2 sounds
- Fixed smaller images not decoding properly at the right resolution. (A very small selection of images fail to decode, they use custom, unsupported formats).