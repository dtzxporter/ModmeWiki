1.  Adding back the restart level option
In BO3, you can only use the restart level button in offline, local mode. With the following patch in your mod, you can add it to every mode, all the time.

1.  Adding the patched file
Download the following file: [[DataSources|https://mega.nz/#!5URygBAZ!tuDTjZI94qURLGZFyYgPXkb6YGIXI-A4lTOi5r6NzVw]] and place it in the following directory

share/raw/ui/uieditor/datasources.luac

Finally open up your mods zone file and add the following line to override the stock one:

rawfile,ui/uieditor/datasources.luac

NOTE: The custom container must end in *.luac because it is a precompiled file!

1.  Final notes
This uses the mod override function to ensure that we load our tweaks first, you may be able to do this in a map via forcefully loading the file under a different name, on load, with the `LuiLoad` function in csc.

//Research Funding://
- Erthrock