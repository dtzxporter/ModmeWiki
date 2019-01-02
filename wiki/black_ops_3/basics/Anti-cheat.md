# Anti-Cheat

Thanks to DidUknowiPwn for making me aware that ModVar was an engine function. 

- Navigate to your mapname.gsc. Example location: `Call of Duty Black Ops III\usermaps\zm_mapname\scripts\zm`
- Scroll to the very bottom of the script and paste this function there:


``` php
function anti_cheat()
{
	ModVar( "god", 0 ); 
	ModVar( "noclip", 0 ); 
	ModVar( "give", 0 ); 
	ModVar( "notarget", 0 ); 
	ModVar( "demigod", 0 ); 
	ModVar( "ufo", 0 );  
}
```

- Go back to the top of your mapname.gsc and find this:

``` php
function main()
{
```
 - **Underneath that,** add the following code:

``` php
level anti_cheat(); 
```


Be sure to give credit to **natesmithzombies** if you are using this script.

---

_Contributors:_
- natesmithzombies
- Koan