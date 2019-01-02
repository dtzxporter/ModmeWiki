Creating A Custom Craftable


Download: [[Everything you need|https://mega.nz/#!EFNEmJDb!vOw-P56mrDii8cyZ3i4E_68ahBUwqArflDpxeqONnJo]]

  *Instructions**

    - Download the files and extract them into your root directory ( Root directory is your Black Ops 3 install )

  *Step 1 : Setting the scripts up**

    - Add the GSC, CSC and GSH to !!root/usermaps/YOUR_MAP_NAME/scripts/zm/craftables/!!
    - Open the GSH, GSC and CSC and replace the references to new ones

    - Open your mapname GSC and CSC from !!root/usermaps/YOUR_MAP_NAME/scripts/zm/!! and add 


1. using scripts\zm\craftables\_zm_craft_template;


  *Step 2 : Add to your zone**

    - Right click your map in launcher and click !!Edit Zone File!!
    - Add the following :


scriptparsetree,scripts\zm\craftables\_zm_craft_template.gsc
scriptparsetree,scripts\zm\craftables\_zm_craft_template.csc
scriptparsetree,scripts\zm\craftables\_zm_craft_template.gsh


  *Step 3 : Radiant**

    - Place the prefabs in your map !!map_source/_prefabs/zm/harrybo21_prefabs/craftabless/!!

  *Step 4 : Compile and Test**

    - In Launcher, tick !!Compile and link!! then click !!Build!!

  *NOTES**

    -when you add your models and shaders to the gsh properly, you will also need to add them to your zone :


xmodel,MODEL_NAME
weapon,WEAPON_NAME


    - You can copy paste this template as many times as you like to create more craftables

  *Contributors**
Harry Bo21
DTZxPorter