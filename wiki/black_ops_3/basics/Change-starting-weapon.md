Go to `BlackOps3Root/usermaps/scripts/zm/` and open the `mapname.gsc` file.

Find this line: `zm_usermap::main();`

Add the following:

lang=php
startingWeapon = "anyweapon";
weapon = getWeapon(startingWeapon);
level.start_weapon = (weapon);

Replace `anyweapon` with a weapon of your choice (for example `smg_standard`).

Save the file and rebuild the mod, you'll have the new starting weapon.

---

//**Contributors:**//
a231