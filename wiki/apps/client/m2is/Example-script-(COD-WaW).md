Below is the install script for COD:WaW:



lang=js
// Modme Install Script: Call of Duty: World at War runner
// A runner is responsible for launching the game, and configuring mods for it

// References segment
var FileSystem = importNamespace("System.IO");

// Launches a game with no mods specifically enabled (No additional requirements)
// (config) is the game-info.json data serialized so we can process it's data
// Valid responses are (success, missing, instance) anything else is marked as unknown
function LaunchGame(rawConfig)
{
      // Parse config
      var GameConfig = JSON.parse(rawConfig);
      // Prepare to launch call of duty world at War
      var GameApplication = internal_LocateGame(GameConfig);
      // Make sure we located the game
      if (GameApplication.mode == "missing")
      {
          // Failed to locate the game
          return "missing";
      }
      else
      {
          // Note: For this game, it makes sense to ask and only use one instance (not required)
          // Check if we're already running and prompt to close if so
          if (GameAPI.ExecutableRunning(GameApplication.path))
          {
              // We have no instances OR closed the running one
              // We located the game, if we have the steam version we must make sure steam is running first
              if (GameApplication.mode == "steam")
              {
                  // Make sure steam is running beforehand
                  SteamAPI.EnsureSteamRunning();
              }
              // Next we must check T4M requirements
              internal_CheckT4MMod(GameConfig);
              // Finally, we can launch the main executable (With arguments if we need to)
              var GameInstance = GameAPI.LaunchExecutable(GameApplication.path, internal_BuildArguments(GameConfig));
              // Ship off instance to game tracker (GameInstance = PID of process)
              GameAPI.TrackGame(GameInstance);
              // We launched the game
              return "success";
          }
          else
          {
              // Failed to launch (Instance running, did not close it)
              return "instance";
          }        
      }    
}

// Internal function to check and or install T4M mod
function internal_CheckT4MMod(GameConfig)
{
      // TODO: T4M settings

}

// Internal function to build runtime arguments for the game
function internal_BuildArguments(GameConfig)
{
      // Builds arguments for the game (Special config types)
      var BuiltArguments = "";
      // We allow certain configuration settings in "game_config" like fullscreen / windowed mode
      if (GameConfig["game_config"]["force_fullscreen"] === "true")
      {
          // We should force fullscreen mode
          BuiltArguments += "+set r_fullscreen 1 ";
      }
      if (GameConfig["game_config"]["force_windowed"] === "true")
      {
          // We should force windowed mode
          BuiltArguments += "+set r_fullscreen 0 ";
      }
      if (GameConfig["game_config"]["enable_cheats"] === "true")
      {
          // We should enable enable_cheats
          BuiltArguments += "+set thereisacow 1 ";
      }
      if (GameConfig["game_config"]["enable_developer"] === "true")
      {
          // We should enable developer mode
          BuiltArguments += "+set developer 1 ";
      }
      // Return the arguments
      return BuiltArguments;
}

// Internal function to find the game's install path
function internal_LocateGame(GameConfig)
{
      // Attempts to find Call of Duty: World at War's main executable
      // Custom path is set if the user overrided the game path
      if (GameConfig["game_config"]["custom_path"] != undefined)
      {
          // We set a custom path, check for the application
          if (FileSystem.File.Exists(FileSystem.Path.Combine(GameConfig["game_config"]["custom_path"], "CoDWaW.exe")))
          {
              // We have a custom (disk) version
              return {"mode" : "disk", "path" : FileSystem.Path.Combine(GameConfig["game_config"]["custom_path"], "CoDWaW.exe")};
          }
      }
      else if (FileSystem.File.Exists(FileSystem.Path.Combine(SystemAPI.GetSystemFolder("programfilesx86"), "Activision\\Call of Duty - World at War\\CoDWaW.exe")))
      {
          // We have the disk version
          return {"mode" : "disk", "path" : FileSystem.Path.Combine(SystemAPI.GetSystemFolder("programfilesx86"), "Activision\\Call of Duty - World at War\\CoDWaW.exe")};
      }
      else if (FileSystem.File.Exists(FileSystem.Path.Combine(SteamAPI.GetSteamDir("Call of Duty World at War"), "CoDWaW.exe")))
      {
          // We have the steam version
          return {"mode" : "steam", "path" : FileSystem.Path.Combine(SteamAPI.GetSteamDir("Call of Duty World at War"), "CoDWaW.exe")};
      }
      // Not found
      return {"mode" : "missing", "path": ""};
}
