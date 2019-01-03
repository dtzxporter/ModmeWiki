# Setting Up Player Voices (Der Eisendrache)

Download: [Everything You Need](https://mega.nz/#!MJkVBBaC!oK16dX_lwDINxUBDZqRIkoZFrnB4_O36RlTtJAGw0dE)

*Instructions*

- Open the download, and copy all the files to your root directory
- This will add all the sounds and aliases that you need to your mod tools

*Scripting:*

- Open your `mapname.gsc`
- Find this line:

``` php
zm_usermap::main();
```

- Underneath add the following :

``` php
level thread zm_castle_vox();
```

- Scroll to the very bottom of the script and add this at the bottom !!not inside any other function!!

``` php
function zm_castle_vox()
{
	zm_audio::loadPlayerVoiceCategories("gamedata/audio/zm/zm_castle_vox.csv");
}
```

*Add the required files to your Zone file:*

- Open your maps **Zone file** ( right click your map in launcher and select **Edit Zone File** )
- Anywhere near the bottom add this :

```
stringtable,gamedata/audio/zm/zm_castle_vox.csv
```

*Setting up the Sounds:*

- Go to `root/usermaps/YOUR_MAP/sound/zoneconfig/`
- You will find a SZC file with your maps name. Open this in any text editor
- Find this section ( Be aware that the copy of the SZC we are originally given is horribly formatted )

``` json
"Sources" : [
{
	"Type" : "ALIAS",
	"Name" : "user_aliases",
	"Filename" : "user_aliases.csv",
	"Specs" : [ ] 
},
```
- add this under it, its pretty much copy paste with the name and filename changed
```json
{
"Type" : "ALIAS",
"Name" : "zm_castle_vox",
"Filename" : "zm_castle_vox.csv",
"Specs" : [ ] 
},
```

*You are DONE*

Ok, so assuming you've followed these steps exactly - Link in launcher. Now go test!

_Contributors:_
- Ardivee
- Zeroy
- Harry Bo21
- DTZxPorter