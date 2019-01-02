1.  Increasing the zombie lobby size
Increasing the lobby size will allow up to 18 player zombie lobbies.

NOTE: You will need to make changes to _zm.gsc and other core scripts to support the addition of more players.

1.  Creating the modified file
Create a file in `share\raw\ui\t7\utility\lobbyutility.lua`

require("ui.t7.utility.lobbyutilityog") -- Ripped original file from Wraith

function Engine.GetLobbyMaxClients()
      Engine.SetDvar("sv_maxclients", 18)
      Engine.SetDvar("com_maxclients", 18)
      Engine.SetLobbyMaxClients(Enum.LobbyType.LOBBY_TYPE_GAME, 18)
      Engine.SetLobbyMaxClients(Enum.LobbyType.LOBBY_TYPE_PRIVATE, 18)
      return 18
end

This will allow 18 players to enter a game. When using this in a mod, you can just overwrite the file using:

rawfile,ui/t7/utility/lobbyutility.lua
rawfile,ui/t7/utility/lobbyutilityog.luac


NOTE: This is for a core_mod zone file

If you're using this in a map, you will need to use csc to force load this using `LuiLoad("ui.t7.utility.lobbyutility");`

NOTE: This will not effect the player score display, the widget has a hardcoded 4 element setup, however, you can modify and create your own that supports more.

Please visit: [[Modifying scripts|http://phabricator.aviacreations.com/w/black_ops_3/intermediate/zombie_lobby_size_%2818_players%29/]] to modify scripts

  *Contributors**
DTZxPorter
Redspace200
HarryBo21
DidUKnowIPwn
LilRobot