# Legion - The Apex Legends Asset Extractor
Extracts various assets from the game "Apex Legends". This software is considered **Work-in-Progress** developed by [DTZxPorter](https://twitter.com/dtzxporter) & id-daemon.

_Download and version info:_

> **IMPORTANT:** By downloading this software you are agreeing to the **EULA** located inside of the archive (EULA.txt).

- Download Link: [Legion (v0.60)](https://mega.nz/#!QJw3iCyB!kzz_BqdLTV6L55BV7Z7XIKx21pg2Wqq3ecjLej9MGtg).
- Requires Visual Studio 2017 x64 Redist: [Redist](https://aka.ms/vs/15/release/vc_redist.x64.exe).
- Currently works as of 3/10/2019 updates.

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
    - Formats: [obj, smd, xnatxt, xnabin] semodel is default.
- After these arguments, just pass the path to the rpak.
- Full example:
  - `--exportmdl --mdlfmt=smd "C:\path\to\apex\paks\Win64\common.rpak"`

> **IMPORTANT:** The tool **AUTO LOADS** the patch rpak files, just specify the base one and it will handle the rest.

## Ripping:
- The **.rpak** files contain various encoded assets that Legion can export; and, as of now the currently supported assets are:
  - Textures in DDS format.
  - DataTables as a CSV file.
  - Models as [SEModel, OBJ, XNALara, SMD].
  
## Coming Soon
- Animations (SEAnim).
- Enhanced GUI.

## Known Bugs:
- A very small handfull of textures aren't supported yet.

## Versioning:
- 0.18 - Initial Release.
- 0.54 - Model export support, fixed patch_master crash, skip existing images.
- 0.60 - Patch rpak support, xmodel_export model format.
