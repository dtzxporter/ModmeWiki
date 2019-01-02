Download: [[Everything You Need|https://mega.nz/#!9cUQRYAT!vYkcwZoPVTweVqaVnjvNygzrbtw08F0BsP7_lVMJuF0]]

https://i.gyazo.com/d0030871b249da4b8e3ce7f8b3b9c08d.gif

  *Instructions**

    - Download the files and extract them into your root directory ( Root directory is your Black Ops 3 install )

  *Radiant:**

Create a spawn point as normal ( or copy paste a existing riser ), but instead of !!riser_location!! you will use !!faller_location!! - everything else remains the same

Make sure the spawn struct is halfway in a ceiling, do not turn it upside down or anything

That is all for radiant

  *You are DONE**

Ok, so assuming you've followed these steps exactly - you now just need to recompile your map and link in launcher. Now go test!

  *Die Rise Elevator Spawners**

https://i.gyazo.com/d0030871b249da4b8e3ce7f8b3b9c08d.gif

I found the animations for the zombies crawling in the elevator shafts from Black Ops 2s !!Die Rise!! are also set up in the script. So I ported those in too

The !!emerge_top!! prefab is a zombie swinging in from above a doorway ( in Die Rise they swung down into open elevator doors ) align the traverse brush so the bottom
lines up with the top of your doorway

The !!emerge_bottom!! prefab is a zombie crawling up into a doorway ( in die rise they crawled up into open elevator doors ) align the traverse brush so the top
lines up with the bottom of your doorway

The !!drop_now!! are like regular fallers, but they emerge almost instantly and drop straight down, just place them anywhere in a ceiling like the others

The !!drop_not_occupied!! is the same but these ones will only spawn here if a player is !!not!! currently in that zone, but !!is!! in a adjacent zone ( not sure why they needed this
but i included it anyway )

The prefabs are located at - !!map_source/_prefabs/zm/harrybo21_prefabs/faller_zombies!!

For all these prefabs, make sure to stamp them, then give the struct the !!targetname!! like normal ( eg !!start_zone_spawners!! )

  *Still to come!**
Moon Jump Pads

  *Contributors**
Harry Bo21
DTZxPorter