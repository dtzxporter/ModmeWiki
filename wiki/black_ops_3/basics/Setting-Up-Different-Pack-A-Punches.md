Download: [[Everything You Need|https://mega.nz/#!ANtnwR5C!unkbrVs3nj32An2leFSEk6Q3udOzjkNZLKL-tp-84Xo]]

  *Instructions**

    - Download the files and extract them into your root directory ( Root directory is your Black Ops 3 install )

    - Copy the scripts from the usermaps OPEN ME folder to your map's script folder

  *Override the stock script:**

- Go to Root/zone_source/all/assetlist

- Open the zm_patch.csv

- Find the two following lines : ( in mine its line 380 and 381 )


scriptparsetree,scripts/zm/_zm_pack_a_punch.csc
scriptparsetree,scripts/zm/_zm_pack_a_punch.gsc


- Comment the two lines out like so


// scriptparsetree,scripts/zm/_zm_pack_a_punch.csc
// scriptparsetree,scripts/zm/_zm_pack_a_punch.gsc


o Dont worry this will not have any negative effect on anything

  *Zone:**

- Open your map's Zone File and add the following line :


include,hb21_pack_a_punches


  *Radiant:**

- Open your map in radiant

- Place which ever boxes you want to use

o The prefabs are located at - map_source/_prefabs/zm/harrybo21_prefabs/pack_a_punch

That is all for radiant

  *Setting up the Sounds:**

Go to root/usermaps/YOUR_MAP/sound/zoneconfig/

You will find a SZC file with your maps name. Open this in any text editor

Find this section ( Be aware that the copy of the SZC we are originally given is horribly formatted )

"Sources" : [
{
	"Type" : "ALIAS",
	"Name" : "user_aliases",
	"Filename" : "user_aliases.csv",
	"Specs" : [ ] 
},

add this under it, its pretty much copy paste with the name and filename changed

{
	"Type" : "ALIAS",
	"Name" : "pack_a_punch_sounds",
	"Filename" : "pack_a_punch_sounds.csv",
	"Specs" : [ ] 
},


  *You are DONE**

- Compile and link your map

- you are DONE

o To fully compile and link your map, tick the "Compile", "Light" and "Link" tick boxes in launcher, and click "Build"

Ok, so assuming you've followed these steps exactly - you now just need to recompile your map and link in launcher. Now go test!

  *Still to come!**


  *Contributors**
Harry Bo21
DTZxPorter