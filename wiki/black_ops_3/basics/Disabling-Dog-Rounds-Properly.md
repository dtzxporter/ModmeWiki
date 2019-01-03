# Disabling Dog Rounds

*Instructions*

Open your `mapname.gsc`

Find this line:

``` php
zm_usermap::main();
```

**Above** it place this line:

``` php
level.dog_rounds_allowed = 0;
```

> **IMPORTANT:** You should still place dog spawners in your map !!in all zones!! as normal - as the default logic Treyarch gave us that makes zombies walk around when you are in zombie blood or downed on solo using Quick Revive, has them target these locations

_Contributors:_
- DTZxPorter
- Harry Bo21