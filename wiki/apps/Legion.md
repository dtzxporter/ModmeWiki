# Legion - The Apex Legends Asset Extractor
<img src="{{ 'LegionBanner.jpg' | relative_link}}" alt="drawing" style="height: 255px; display:block;"/>
Extracts various assets from the game "Apex Legends". This software is considered **Work-in-Progress** developed by [DTZxPorter](https://twitter.com/dtzxporter) & id-daemon.

_Download and version info:_

> **IMPORTANT:** By downloading this software you are agreeing to the **EULA** located inside of the archive (EULA.txt).

- Download Link: [Legion (v1.02)](https://mega.nz/#!UcBiDASB!oOd1If8jZ_L2cIWOXCVyQ_5ulhk0o9m4WLeCdwq0Siw).
- Requires Visual Studio 2019 x64 Redist: [Redist](https://aka.ms/vs/16/release/vc_redist.x64.exe).
- Currently works as of 7/17/2019 updates.

## 🎂 Beta v2.00:
- Download Link: [Legion Beta (v2.00)](https://mega.nz/#!EU41UYyZ!_BqzIx7YTBxBKSaaibSLziWFNfYhbnASWksXiiYzLBI).
- Requires Visual Studio 2019 x64 Redist: [Redist](https://aka.ms/vs/16/release/vc_redist.x64.exe).
- Sound/Audio only beta.

## Donate:
- I take time out of my day to make this happen.
- Show your support: [HERE](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=686S5QL7Z4HKQ)

## Usage:
Using Legion is fairly simple as the tool only requires the files located within "Apex\paks\Win64" in order to function.
> **IMPORTANT:** Both the tool and the game **require** the entirety of the Win64 folder to be intact and must not be modified in any way.

- The tool supports Drag and Drop functionality, supported file formats are ONLY the **.rpak** extensions.

## Command Line:
- By default, Legion exports textures and data tables.
- To switch mode to models add:
  - `--exportmdl` as the first argument.
  - `--mdlfmt=obj` switches the model format.
    - Formats: [obj, smd, xnatxt, xnabin, xmodel, maya, fbx] semodel is default.
- To switch mode to animations add:
  - `--exportanim` as the first argument.
- To change the image format add:
  - `--imgfmt=png` switches the image format.
    - Formats: [png, tiff] dds is default.
- After these arguments, just pass the path to the rpak.
- Full example:
  - `--exportmdl --mdlfmt=smd "C:\path\to\apex\paks\Win64\common.rpak"`

> **IMPORTANT:** The tool **AUTO LOADS** the patch rpak files, just specify the base one and it will handle the rest.

> **NOTE:** Not all (0X).rpak files are patches, some can be loaded directly, just try them.

## Ripping:
- The **.rpak** files contain various encoded assets that Legion can export; and, as of now the currently supported assets are:
  - Textures as [Dds, Png, Tiff]
  - DataTables as a CSV file.
  - Models as [SEModel, OBJ, XNALara, SMD, CoD XModel, Maya (Legacy), Kaydara FBX].
  - Animations as [SEAnim].
  
## Notice:
- SE* formats (SEModel, SEAnim are preferred over any other export format and have guaranteed compatibility).

## Desktop Wallpaper:
- A slick wallpaper for Legion (By @Spooky_Sal): [Download](https://mega.nz/#!1dh2yaBY!krhTFxou3eYwrl98XVnS40fvUS69wVMVm4pLd8Oo-GM)
- An electrifying poster for Legion S2 (By @Spooky_Sal): [Download](https://mega.nz/#!ABBGkKza!0L_YWs-T6TGMcEBnBvk9UqMaVhxvN5oUatIGAPN8KY8)

## Versioning:
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