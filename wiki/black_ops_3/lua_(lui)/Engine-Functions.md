1.  Engine functions with description
Below is a list of the important engine functions that you may find useful. All functions are under the namespace `Engine`

1.  IsCampaignGame()
Returns whether or not the current gamemode is campaign.

1.  IsZombiesGame()
Returns whether or not the current gamemode is zombies.

1.  IsMultiplayerGame()
Returns whether or not the current gamemode is multiplayer.

1.  IsCampaignModeZombies()
Returns whether or not the current gamemode is campaign-zombies.

1.  IsDOAGame()
Returns whether or not the current gamemode is dead ops arcade.

1.  IsMenuLevel()
Returns whether or not the current gamemode is the main menu level.

1.  CurrentTime()
Returns the current time.

1.  ToUpper(String: value)
Returns the string as an all uppercase one.

1.  ToLower(String: value)
Returns the string as an all lowercase one.

1.  Exec(String: value)
Executes the command in the current console instance.

1.  GetLocalClientNum()
Gets the current users local client number.

1.  GetMOTD()
Gets the current message of the day.

1.  GetGlobalModel()
Returns the global ui model for use with controller events.

1.  IsControllerUsed()
Returns whether or not the user is using a controller.

1.  IsLocalClient()
Returns whether or not you are a local client.

1.  UnpackRgba(Number: value)
Unpacks a RGBA color hex int to a color object.

1.  Localize(Object: value)
Converts an object to an engine localized version in string form.

1.  GetTimeRemainingString()
Gets the current time remaining in the gamemode.

1.  GetGametypeName()
Gets the name of the current gametype.

1.  UnsubscribeAndFreeModel()
Unsubscribe (Detatch) and clear the current engine model.

1.  PlaySound(String: value)
Plays the sound asset with the given name.

1.  ForceHUDRefresh()
Forces the hud to redraw.

1.  Is4K()
Returns whether or not the user is using a 4k resolution.

1.  GetLobbyMaxClients(Enum.LobbyType: lobbyType)
Returns the max number of clients this lobby supports.

1.  GetCurrentMap()
Returns the name of the currently loaded map, example: `zm_zod`.

1.  SetDvar(String: name, Object: value)
Sets the DVar with the given name and value. The value type must be the same as the DVar type.

1.  SetModelValue(Object: model, Object: value)
Sets the value on the given model to the value provided.

1.  GetModelValue(Object: model)
Gets the current value for a model.

1.  CreateModel(Object: controller, String: name)
Creates a new model on the given controller with the provided name.

1.  GetUserSafeAreaForController(Object: controller)
Returns the safe area margins for the given controller: (left, right, top, bottom).

1.  GetFullPlayerName(Object: controller | Number: clientnum)
Returns the full name of the player with the given client number or controller (Gamertag / SteamID / PSN)