# Perfect-Heist-2-LUA-Modding
This repo provides guides and references for creating custom scripts, actors, and classes for the game Perfect Heist 2. Make sure to visit the game's Discord for more information and discussions:  https://discord.gg/QT8vEBzHQf 


---

## 📖 Documentation

| File | Description |
|------|-------------|
| [Hooks.md](Hooks.md) | All available events you can listen to |
| [Functions.md](Functions.md) | All global Lua functions available to modders |
| [Reflection.md](Reflection.md) | Game classes, their variables, and callable functions |

---

## Quick Overview

Perfect Heist 2 mods are written in **Lua** and organized into **Modpacks**. A modpack is a folder containing scripts and assets that add new gameplay, actors, and classes to the game. 

Modpacks can be uploaded to the Steam Workshop and added to your game session through the `Host Game` menu or through the `[ModpackOverride] ModpackList = AbsoluteModpackPath1, AbsoluteModpackPath2` server config setting. Modpacks can also be included in player-created custom maps, ensuring they always run with the map. All scripts are loaded when the team selection begins, and are destroyed after the Round-End UI.

### Modpack Folder Structure

```
MyModpack/
├── ServerScripts/        # Scripts that run game logic (round events, rules)
│   ├── MyScript.lua      # Event-Driven Logic that runs during the round
├── ActorScripts/         # Scripts for custom interactable actors (BP_LuaActor)
│   ├── MyActor.lua       # Actor that can be placed on custom maps, and spawned through other scripts
├── CustomClassScripts/   # Scripts + JSON for custom player classes
│   ├── MyClass.lua       # Ability logic
│   └── MyClass.json      # Class display info (name, icon, cooldown, etc.)
├── Assets/               # Sound files (.wav, .mp3), textures (.png), meshes (.fbx)
│   ├── AbilityIcon.png   # Icons referenced by custom classes
│   └── Woosh.mp3         # Audio files (.mp3 or .wav) referenced by LUA scripts in this modpack
│   ├── CrateMesh.fbx     # .fbx files referenced by ActorScripts - try to keep size as small as possible
│   ├── CrateTexture.png  # .png textures for the custom .fbx meshes - try to keep size as small as possible
├── modinfo.json          # Steam Workshop metadata
├── name.txt              # Display name of the modpack
├── description.txt       # Modpack description
└── preview.jpg           # Preview image for Workshop
```

---

## Getting Started

### 1. Create a Modpack

In the in-game **Level Editor**, locate the Modpack Window in the bottom left and click **Modpacks -> New** and give it a name. This creates the folder structure above in your `Saved/Modpacks/` directory.

### 2. Create a Script

Choose a category and create a new script. The game generates boilerplate code for you. Click **Edit File** icon to edit the `.lua` file in your preferred text editor (Notepad, VS Code, etc.).

### 3. The Event System

All mod logic is driven by **events**. You register a function to run when a specific event fires:

```lua
ListenToEvent("RoundStarted", function()
    LogMessage("The round has started!")
end)
```

Events have a **server** version and a **client** version. Client events end with `_OnClient`:

```lua
-- Runs on the server
ListenToEvent("RoundStarted", function()
    LogMessage("SERVER: Round started!")
end)

-- Runs on each client
ListenToEvent("RoundStarted_OnClient", function()
    LogMessage("CLIENT: Round started!")
end)
```

### 4. Working with Actors

Actors (players, objects, doors, etc.) are passed to your event callbacks. You can read their variables and call their functions:

```lua
ListenToEvent("ActorSpawned", function(targetActor)
    local name = GetActorName(targetActor)
    LogMessage("An actor spawned: " .. name)

    -- Read a Blueprint variable
    local health = targetActor.Health

    -- Call a Blueprint function
    targetActor:SetActorHiddenInGame(true)

    -- Access sub-components
    local mesh = targetActor.Mesh
    mesh:SetVisibility(false)
end)
```

> **Important:** Use **colon syntax** (`:`) when calling functions on actors. Dot syntax (`.`) is for reading variables.


### 5. Testing Modpacks

Make sure you currently have a custom map loaded inside the Level Editor. Then, inside the selected Modpack UI, make sure to check `Include With Map`. Then just hit playtest, and all scripts inside the modpack should be running, including custom classes. To test custom actors, place a `LUA Object` level editor object on your map, and make sure to enter a valid filename, like `TestScript.lua`.

### 5. Uploading Modpacks

Once you are finished working on your modpack, you can click on the `Upload to Steam` button, and a new Steam Workshop file will be created for your Modpack, using your specified Modpack Name in the `%APPDATA%\Local\PerfectHeist2\Saved\Modpacks\YourModpackName\name.txt`. When the upload is finished, the Steam Workshop page will open automatically. Uploading a modpack with an existing Steam Workshop page will update that Workshop Object instead.

If you chose to include a modpack in your custom map by toggling `Include With Map`, the modpack will be automatically uploaded with your map when you upload the map to the Steam Workshop.

---

## Script Types

### Server Scripts

General-purpose scripts for game logic. They react to round events and can affect any actor in the world.

```lua
LogMessage("Loaded MyServerScript.lua")

ListenToEvent("RoundStarted", function()
    local players = GetPlayerChars()
    for i, player in ipairs(players) do
        LogMessage("Player: " .. GetActorName(player))
    end
end)
```

### Actor Scripts

Scripts associated with a **BP_LuaActor** - a customizable in-world actor. Each BP_LuaActor has a `LuaFileName` property that links it to its script. Actor scripts define initialization, visual setup, interactions, and they can receive any event specified in [Hooks.md](Hooks.md).

```lua
LogMessage("Loaded MyActor.lua")

-- Initialize when the actor spawns
ListenToEvent("ActorSpawned", function(targetActor)
	-- ListenToEvent listenes to ALL events with that name, so we need to make it's the one this script handles
    if targetActor.LuaFileName == "MyActor.lua" then
		-- Calling SetReplicatedVar(Name, Value) on the server will propagate this value to all clients.
		-- Server and Clients can get this value with local value = GetReplicatedVar(Name)
		-- SetLocalVar(Name, Value) and GetLocalVar(Name) should be used for clients or when the server value doesn't need to be replicated
        targetActor:SetReplicatedVar("UsesLeft", "3")
    end
end)

-- Client: Show interaction prompt
ListenToEvent("GetInteractName_OnClient", function(targetActor, playerActor)
    if targetActor.LuaFileName == "MyActor.lua" then
        local uses = tonumber(targetActor:GetReplicatedVar("UsesLeft"))
        if uses and uses > 0 then
			-- This defines the InteractionString and bCanInteract values ONLY FOR THE CLIENT that executed this event by looking at the Actor
			-- Since every client figures this out for themselves, you can allow for different interactions or block interaction completely
			-- depending on the team, class, or other variables of the player who is trying to interact with it
            targetActor.InteractionString = "Use (" .. uses .. " left)"
            targetActor.bCanInteract = true
        else
            targetActor.InteractionString = "Empty"
            targetActor.bCanInteract = false
        end
    end
end)

-- Client: How long the interaction takes (seconds)
ListenToEvent("GetInteractionTimer_OnClient", function(targetActor, playerActor)
    if targetActor.LuaFileName == "MyActor.lua" then
		-- Like InteractionString and bCanInteract, this sets the interaction duration in seconds ONLY FOR THE CLIENT that executed this event by looking at the Actor
        targetActor.InteractionTimer = 2.0
    end
end)

-- Server: Handle the interaction
-- InteractSV is called by the client when he finished his InteractionTimer and bCanInteract was true for him
-- This Event is called by the client, but will never run for him. He just sends it to the server when he calls it, and the server is responsible for handling the interaction
ListenToEvent("InteractSV", function(targetActor, playerActor)
    if targetActor.LuaFileName == "MyActor.lua" then
        local uses = tonumber(targetActor:GetReplicatedVar("UsesLeft"))
        if uses and uses > 0 then
            targetActor:SetReplicatedVar("UsesLeft", tostring(uses - 1))
            LogMessage(GetActorName(playerActor) .. " used the actor!")
        end
    end
end)
```

### Custom Class Scripts

Custom classes require **two files** with the same name: a `.json` for display data and a `.lua` for ability logic.

List of Weapon IDs: `1=Rifle, 2=SMG, 3=Auto Sniper, 4=Pistol, 5=Rocket Launcher, 6=Shotgun, 7=Grappling Hook, 8=Silenced Pistol, 9=Smoke Launcher, 10=Grenade Launcher, 11=Teargas Launcher, 12=Automatic Pistol, 13=Sniper Rifle, 14=Decoy Launcher, 15=Carbine, 16=Bullpup MP, 17=Tommy Gun, 18=Taser, 19=Sticky Launcher, 20=Heavy Pistol, 21=Modified Pistol, 22=Silenced Rifle, 23=Flash Launcher, 24=Rope Launcher, 25=Syringe Gun, 26=Slug Shotgun, 27=Geiger Counter, 28=Chrono-Nade Launcher, 29=Sceptre, 30=Dagger, 31=Hammer, 32=Sickle, 33=Bottle, 34=Bottle, 35=Gladius, 36=T-Shirt Cannon, 37=Drone Remote, 38=Wrench`

List of Clothing Rows: `Customer_Hoodie_Red, Customer_Jacket_Green, Customer_Hoodie_Black, Customer_Jacket_Red, Employee_PurpleTie, Employee_RedTie, Cook, Cop_1, Cop_2, Cop_3, Cop_4, DEA_Female_1, DEA_Female_2, DEA_Female_3, DEA_Female_4, DEA_Male_1, DEA_Male_2, DEA_Male_3, DEA_Male_4, Spy_Male, Spy_Female`

**Assassin.json:**
```json
{
    "IsRobber": true,
    "DisplayName": "Assassin",
    "ClothingRowName": "Robber_Suit_Black",
    "AbilityName": "Cloak",
    "AbilityDescription": "Turn invisible for 5 seconds.",
    "AbilityIcon": "AssassinAbility.png",
    "AbilityCooldown": 30.0,
    "PassiveName": "Silent Steps",
    "PassiveDescription": "Footsteps make no sound.",
    "PassiveIcon": "SilentStepsIcon.png",
    "PrimaryWeapon": 1,
    "SecondaryWeapon": 2,
    "ClassCategory": 0
}
```

`AssassinAbility.png` and `SilentStepsIcon.png` need to exist in the Modpacks /Assets/ folder.

**Assassin.lua:**
```lua
LogMessage("Loaded Assassin.lua")

ListenToEvent("AbilityKeyPressed_OnClient", function(playerActor)
    if playerActor.CustomClassString == "Assassin" then
        LogMessage("CLIENT: Assassin cloaking!")

        playerActor:StartAbilityCooldown(6.0)

        -- AbilitySV is called on the client player, but the function executes on the server who can then handle the logic and replication to all other clients
        playerActor:AbilitySV()

        -- Play a sound locally only for this player, so he knows he activated his ability
		PlaySound(playerActor, "Woosh.mp3", 0.8)

		-- Show a message at the top center of the player screens for 5 seconds
		ShowUIText("InvisibilityNotification", "Invisible!", 0.5, 0.2, 5.0)	
    end
end)

ListenToEvent("AbilitySV", function(playerActor)
    if playerActor.CustomClassString == "Assassin" then
        LogMessage("SERVER: Assassin cloaking!")

        -- Setting the .Mesh of the playerActor to hidden. We don't want to set the whole player character hidden, since this logic is getting overwritten by the game code.
        -- Certain functions like SetHiddenIngame automatically propagate to all clients if called on the server.
        -- If you need to execute code on ALL clients instead of just the server for an ability, you can call AbilityALL() on the server, and it will execute on all clients
        playerActor.Mesh:SetHiddenIngame(true)

        -- Setting his FP_Arms (the first person viewmodel) to hidden as well, so the player who used the ability can see something happen on his screen for additional feedback
		playerActor.FP_Arms:SetHiddenIngame(true)

        -- Setting the .preventShooting variable of the player character class to true, so he can't fire while invisible
		playerActor.preventShooting=true

        -- Starting a timer on the playerActor object so he will call LUA back in 5 seconds with the "AssassinUncloak" function
        SetTimer(5.0, "AssassinUncloak", playerActor)
    end
end)

ListenToEvent("AssassinUncloak", function(playerActor)
    playerActor.Mesh:SetHiddenIngame(false)
	playerActor.FP_Arms:SetHiddenIngame(false)
	playerActor.preventShooting=false
    LogMessage("SERVER: Assassin visible again!")
end)
```

---

## Replicated vs Local Variables

BP_LuaActors and PlayerChars have a key-value storage system for custom variables.

**Replicated variables** are set on the server and automatically sync to all clients:

```lua
-- Server sets it
targetActor:SetReplicatedVar("UsesLeft", "3")

-- Client can read it (synced automatically)
local uses = targetActor:GetReplicatedVar("UsesLeft")
```

**Local variables** only exist on the machine that sets them:

```lua
-- Only exists on this client
targetActor:SetLocalVar("UIState", "highlighted")
local state = targetActor:GetLocalVar("UIState")
```

> **Note:** All values are stored as strings. Use `tonumber()` when you need to do math:
> ```lua
> local uses = tonumber(targetActor:GetReplicatedVar("UsesLeft"))
> if uses and uses > 0 then
>     targetActor:SetReplicatedVar("UsesLeft", tostring(uses - 1))
> end
> ```

---

## Custom Meshes and Sounds

### Adding Mesh Components to Actors

Place `.fbx` and `.png` files in your modpack's `Assets/` folder:

```lua
ListenToEvent("ActorSpawned", function(targetActor)
    if targetActor.LuaFileName == "MyActor.lua" then
        AddMeshComponent(targetActor, "Base", "MyMesh.fbx", "MyTexture.png")

        local base = GetMeshComponent(targetActor, "Base")
        base:SetRelativeLocation({X=0, Y=0, Z=0})
        base:SetRelativeScale3D({X=1, Y=1, Z=1})
        base:SetRelativeRotation({Pitch=0, Yaw=90, Roll=0})
    end
end)
```

### Playing Sounds

Place `.wav` or `.mp3` files in your modpack's `Assets/` folder:

```lua
-- PlaySound(actor, filename, volume)
PlaySound(playerActor, "Woosh.wav", 0.8)
PlaySound(targetActor, "Explosion.mp3")  -- volume defaults to 1.0
```

---

## UI

### Showing Text on Screen

```lua
-- ShowUIText(identifier, text, x, y, displayTimeSeconds)
-- x and y range from 0 to 1 (screen position)
-- displayTime of 0 = stays until updated or removed

-- Show a kill feed message at top center for 3 seconds
ShowUIText("KillFeed", "Player eliminated Target!", 0.5, 0.1, 3.0)

-- Persistent HUD element
ShowUIText("AmmoCount", "Ammo: 12", 0.9, 0.9, 0)

-- Update existing element (same identifier)
ShowUIText("AmmoCount", "Ammo: 11", 0.9, 0.9, 0)
```

---

## Timers

Use `SetTimer` to execute an event after a delay:

```lua
-- SetTimer(seconds, eventName, actor)
SetTimer(5.0, "MyDelayedEvent", targetActor)

ListenToEvent("MyDelayedEvent", function(actor)
    LogMessage("5 seconds have passed!")
end)
```

---

## Networking Tips

- **Server events** handle authoritative game logic (damage, scoring, state changes)
- **Client events** (ending in `_OnClient`) handle visuals, sounds, and UI
- Use **replicated variables** (`SetReplicatedVar` / `GetReplicatedVar`) to sync data from server to clients
- Use **local variables** (`SetLocalVar` / `GetLocalVar`) for client-only data
- When calling a function that should run on the server from the client, use existing RPCs like `playerActor:AbilitySV()`
- The event system automatically appends `_OnClient` when running on a client — you don't need to manage this yourself

---

## Common Patterns

### Filtering by Actor Type

```lua
ListenToEvent("ActorSpawned", function(targetActor)
    if targetActor.LuaFileName == "HealthStation.lua" then
        -- Only runs for HealthStation actors
    end
end)
```

### Filtering by Class

```lua
ListenToEvent("AbilitySV", function(playerActor)
    if playerActor.CustomClassString == "Assassin" then
        -- Only runs for Assassin players
    end
end)
```

### Checking Actor Class Type

```lua
local pawn = GetPlayerPawn()
local className = GetActorClassName(pawn)

if className == "PlayerChar" then
    LogMessage("Player is on foot")
elseif className == "TechDrone" then
    LogMessage("Player is flying a drone")
end
```

### Finding Actors in the World

```lua
-- By class name
local doors = GetAllActorsOfClass("SafeDoor")

-- By tag
-- Tags can be added to Lua Objects in the level editor, or modified by LUA scripts at runtime using:
-- AddActorTag(targetActor, "AssassinTarget") and RemoveActorTag(targetActor, "AssassinTarget")
local targets = GetAllActorsWithTag("AssassinTarget")
local target = GetActorWithTag("AssassinTarget")

-- Check if an actor has a specific tag
if ActorHasTag(targetActor, "AssassinTarget") then
    LogMessage("This actor is an AssassinTarget!")
end

-- All controlled pawns (whatever the PlayerControllers are currently controlling, usually it's a PlayerChar, but it can also be a drone or horse)
local pawns = GetAllControlledPawns()

-- The Player's player character, no matter what he currently controls
local pc = GetPlayerController()
local playerChar = pc.PlayerChar

-- All playerChars
local players = GetAllActorsOfClass("PlayerChar")

-- Closest actor of a class to a location
local closest = GetClosestActor("SafeDoor", {X=100, Y=200, Z=0})
```

### Accessing Game Framework

```lua
local gs = GetGameState()
local gm = GetGameMode()
local pc = GetPlayerController()
local pawn = GetPlayerPawn()

-- Call functions on them
gm:RoundWon_GM(true, 0)
```

---

## Debugging

Use `LogMessage` to print to the game's output log:

```lua
LogMessage("Hello from Lua!")
LogMessage("Health: " .. tostring(player.HP))
LogMessage("Steam Name: " .. tostring(player.PlayersName))
LogMessage("Actor: " .. GetActorName(targetActor))
```

Check the logs at: `%APPDATA%/Local/PerfectHeist2/Saved/Logs/PerfectHeist2.log`.

Or use on-screen HUD messages:

```lua
ShowUIText("DebugLog", "Actor: " .. GetActorName(targetActor), 0.5, 0.1, 3.0)
ShowUIText("DebugLog", "Health: " .. tostring(player.HP), 0.5, 0.15, 3.0)
ShowUIText("DebugLog", "Steam Name: " .. tostring(player.PlayersName), 0.5, 0.2, 3.0)
```
