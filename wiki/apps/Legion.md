# Legion - The Apex Legends Asset Extractor
Extracts various assets from the game "Apex Legends". This software is considered **Work-in-Progress** developed by [DTZxPorter](https://twitter.com/dtzxporter). The current release v0.18 is a **demo** of what the tool is going to be capable of. Porter is working on the tool on his spare time, if you'd like to show your support to Porter for his work you can do so [here](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=686S5QL7Z4HKQ).

_Download and version info:_

> **IMPORTANT:** By downloading this software you are agreeing to the **EULA** located inside of the archive (EULA.txt).

- Download Link: [Legion (v0.18 demo)](https://mega.nz/#!sEoRnAbQ!pB2S_5VubXUgJoMItl5Jx8YtExnSrubVnwhG2i6zRUM).
- Requires Visual Studio 2017 x64 Redist: [Redist](https://aka.ms/vs/15/release/vc_redist.x64.exe).
- Currently works as of 3/10/2019 updates.


## Usage:
Using Legion is fairly simple as the tool only requires the files located within "Apex\paks\Win64" in order to function.
> **IMPORTANT:** Both the tool and the game **require** the entirety of the Win64 folder to be intact and must not be modified in any way.

- The tool supports Drag and Drop functionality, supported file formats are ONLY the **.rpak** extensions.

> **IMPORTANT:** The tool only supports non-patched rpaks right now; so files such as "common(02).rpak" are currently **unsupported**.

## Ripping:
- The **.rpak** files contain various encoded assets that Legion can export; and, as of now the currently supported assets are:
  - Textures in DDS format.
  - DataTables as a CSV file.
- Models and possibly animations are coming soon.

## Known Bugs:
- A very small handfull of textures aren't supported yet.
- patch_master.rpak will crash the tool, but has nothing in it anyways.

## Versioning:
- 0.18 - Initial Release.
