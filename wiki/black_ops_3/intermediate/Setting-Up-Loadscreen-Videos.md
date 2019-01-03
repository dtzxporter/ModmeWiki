# Setting Up Loadscreen Videos
This tutorial will go over properly setting up a solo load screen video (With working audio!)

> **WARNING:** Please take your time when following this tutorial as it's more in-depth!

## Preparing your video file
You will need to have a video prepared for use with your mod. The video must have it's audio separated in a different file, as we will have to add it separately in order for it to work properly.

## Converting the video file
To convert the video properly, we'll use a tool called handbrake [Download](https://handbrake.fr/). With handbrake, you can provide the input video file for use when transcoding. Using the presets on the right, you can select 720p30fps as a base. In the format dropdown, select `MKV` format. Finally before exporting, you must go to the audio tab and **remove** any existing tracks. The video file will not play otherwise.

{F13258}

To recap the settings:
- The format must be `MKV`
- There must be NO audio tracks
- H.264 encoding
- Select 720p30fps as a base

## Preparing the audio file
The only thing that matters here is that we have a 48kHz (Or any with snd_patcher) `WAV` formatted audio file for use with the cutscene.

## Setting up the video
To setup a video file for use with your map, you must navigate to `<bo3root>\usermaps\mapname\zone\` and make a folder called `video`. Rename your resulting `MKV` file from earlier as `zm_mapname_load` and place it in the video folder. Note that all assets will properly upload to steam. With this file present, the game will now load and play the video when loading your map in solo.

## Setting up the audio
This is the more tricky part, due to the fact that as of right now, it requires you to use an additional mod with your map file. In launcher, create a new `Mod` and name it whatever. When building, just check off `zm_mod`. Navigate to `<bo3root>\mods\modname\zonesource\` and open the zm_mod config file with a text editor. At the bottom add the following line:

```
sound,zm_mod
```

## Setting up the sound config
Mods, by default do not include a sound zone file. It is easiest to copy the files from an existing mod so navigate to your already in progress map zone `<bo3root>\usermaps\mapname\` and copy the sound files including the `.szc` file. When copying it to your mod folder, rename the `.szc` file to `zm_mod.szc` this is to prevent a converter error when linking the mod.

Now, open up the `.scz` file and modify the name line to `zm_mod` to match the file name.

> **NOTE:** You may change the name of the alias file (user_aliases.csv) here so you can have another alias file just for the mod

## Adding the required alias line
Now that we have our mod using an alias file, we can add the required line for the video. Below is an example alias line, when copying data from it, be sure to put the information in the correct columns!

```
Name,FileSpec,Template,Loadspec,Secondary,VolumeGroup,VolMin,VolMax,DistMin,DistMaxDry,DistMaxWet,DryMaxCurve,WetMaxCurve,DryMinCurve,WetMinCurve,LimitCount,LimitType,EntityLimitCount,EntityLimitType,PitchMin,PitchMax,PriorityMin,PriorityMax,PriorityThresholdMin,PriorityThresholdMax,PanType,Storage,Looping,RandomizeType,Probability,StartDelay,ReverbSend,Duck,Pan,CenterSend,EnvelopMin,EnvelopMax,EnvelopPercent,OcclusionLevel,IsBig,DistanceLpf,FluxType,FluxTime,Subtitle,Doppler,dopplerscale,Futz,ContextType,ContextValue,contexttype1,contextvalue1,contexttype2,contextvalue2,Compression,Timescale,IsMusic,FadeIn,FadeOut,Pauseable,StopOnEntDeath,Bus,DuckGroup,iscinematic

bik_zm_testmap_load,tst\testsound.wav,CIN_C_MOD,,,,,,,,,,,,,,,,,,,,,,,,,,,,,0,,,,,,,,,,,,,,,,,,,,,,,,,,,yes,,,,
```
> **NOTE:** I highly recommend copying this into an Excel Sheet so it's easier to edit.

The main slots to take into account are:
- Name: It is always going to be `bik_zm_mapname_load`
- Template: It will always be CIN_C_MOD, this is a cinematic base template
- Pausable: Allows the audio to stop playing early, or when skipping

After linking your mod again, and launching solo, it should play the video and audio in sync, just like stock maps.

## Closing and ease of use
Now, since this requires a mod, you can make it easier on people when playing your map by linking the mod as a dependency on the steam workshop. The mod dependency will show up on the right hand side of the page, and download with the map. In addition, using a mod like this can give your map an added layer of security since you can only have one mod and map loaded at once, and you can make your map depend on your specific mod.

> **NOTE:** If you still don't have audio playing it's possible that the converter failed, you can use Wraith to open your mod sab file to verify that it converted properly.
