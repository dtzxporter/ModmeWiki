1.  Overriding a map level hud
To override the hud in a zombies map level you must use a different file name as you can't override `FILES` at a zone level, however, Lua itself makes this easy.

1.  Preparing your hud
First, you must still be using our factory hud base `LUI.createMenu.T7Hud_zm_factory` as a root function. However, this time we're gonna give the file a different name. Instead of `t7hud_zm_factory.lua`, lets name it `t7hud_zm_custom.lua`.

1.  Changing your zone entry
Now that you renamed the hud, rename your zone entry:

rawfile,ui/uieditor/menus/hud/t7hud_zm_custom.lua


1.  Loading our custom hud, overriding the giant hud
To load our custom hud we must open our `mapname.csc`, inside the `main()` function we must tell Lua to load our file:

function main()
{
          // Load our custom hud, at this point, the giant hud is already loaded, and we override the function!
          LuiLoad( "ui.uieditor.menus.hud.t7hud_zm_custom" );

	zm_usermap::main();

	include_weapons();
	util::waitforclient( 0 );
}

That is all you need to override the hud from a map. Mods, however, can override any lua file.