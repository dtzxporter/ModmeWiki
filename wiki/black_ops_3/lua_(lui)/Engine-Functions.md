# Engine Functions

Below is a list of the important engine functions that you may find useful. All functions are under the namespace `Engine`

- IsCampaignGame()
Returns whether or not the current gamemode is campaign.
- IsZombiesGame()
Returns whether or not the current gamemode is zombies.
- IsMultiplayerGame()
Returns whether or not the current gamemode is multiplayer.
- IsCampaignModeZombies()
Returns whether or not the current gamemode is campaign-zombies.
- IsDOAGame()
Returns whether or not the current gamemode is dead ops arcade.
- IsMenuLevel()
Returns whether or not the current gamemode is the main menu level.
- CurrentTime()
Returns the current time.
- ToUpper(String: value)
Returns the string as an all uppercase one.
- ToLower(String: value)
Returns the string as an all lowercase one.
- Exec(String: value)
Executes the command in the current console instance.
- GetLocalClientNum()
Gets the current users local client number.
- GetMOTD()
Gets the current message of the day.
- GetGlobalModel()
Returns the global ui model for use with controller events.
- IsControllerUsed()
Returns whether or not the user is using a controller.
- IsLocalClient()
Returns whether or not you are a local client.
- UnpackRgba(Number: value)
Unpacks a RGBA color hex int to a color object.
- Localize(Object: value)
Converts an object to an engine localized version in string form.
- GetTimeRemainingString()
Gets the current time remaining in the gamemode.
- GetGametypeName()
Gets the name of the current gametype.
- UnsubscribeAndFreeModel()
Unsubscribe (Detatch) and clear the current engine model.
- PlaySound(String: value)
Plays the sound asset with the given name.
- ForceHUDRefresh()
Forces the hud to redraw.
- Is4K()
Returns whether or not the user is using a 4k resolution.
- GetLobbyMaxClients(Enum.LobbyType: lobbyType)
Returns the max number of clients this lobby supports.
- GetCurrentMap()
Returns the name of the currently loaded map, example: `zm_zod`.
- SetDvar(String: name, Object: value)
Sets the DVar with the given name and value. The value type must be the same as the DVar type.
- SetModelValue(Object: model, Object: value)
Sets the value on the given model to the value provided.
- GetModelValue(Object: model)
Gets the current value for a model.
- CreateModel(Object: controller, String: name)
Creates a new model on the given controller with the provided name.
- GetUserSafeAreaForController(Object: controller)
Returns the safe area margins for the given controller: (left, right, top, bottom).
- GetFullPlayerName(Object: controller | Number: clientnum)
Returns the full name of the player with the given client number or controller (Gamertag / SteamID / PSN)