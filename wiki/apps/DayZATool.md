# DayZATool - DayZ animation / skeleton tool
Extracts animations/models and generates animations for DayZ Tools. Developed by [DTZxPorter](https://twitter.com/dtzxporter).

_Download and version info:_

> **IMPORTANT:** By downloading this software you are agreeing to the **EULA** located inside of the archive (EULA.txt).

- Download Link: [DayZATool](https://mega.nz/#!wURCmCLD!aX_KdkZ2RBfuQ0JoBDN7rLxT-Dd75uPL1dWv2EcIoqo).
- Requires .NET Framework (4.5): [Download](https://www.microsoft.com/en-us/download/details.aspx?id=30653).

## Donate:
- I take time out of my day to make this happen.
- Show your support: [HERE](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=686S5QL7Z4HKQ)

## Usage:
Using DayZATool just requires one of the following formats:
- anm (For extraction)
- xob (For extraction)
- seanim (For generate)

## Command Line:
- By default, It will show the usage.
  - `--command input scale invert`.
- To extract anm files to seanim files:
  - `--extract-anim file.anm`
- To extract xob files to semodel files:
  - `--extract-mdl file.xob`
- To create a new anm file from a seanim:
  - `--generate-anim file.seanim`

> **NOTE:** You may have to play with the scale of the animation

> **SCALE:** Default scale is 100. That means that extraction does *= 100 on translations and generate does /= 100. To change the scale, the third parameter accepts a float value. 1 meaning no scale change.

## Notice:
- SE* formats (SEModel, SEAnim are my open-sourced model and animation format, get the plugins here):
   - [SETools Maya](https://github.com/dtzxporter/SETools)
   - [io_scene_seanim](https://github.com/SE2Dev/io_anim_seanim)
   - [io_scene_semodel](https://github.com/dtzxporter/io_model_semodel)

## Versioning:
- 1.00 - Initial release.
- 1.20 - Support for complete models instead of skeletons.
- 1.30 - Support for XOB8HEAD models.
- 1.40 - Added flag to invert left/right bones.