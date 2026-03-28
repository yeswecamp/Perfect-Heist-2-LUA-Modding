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

Perfect Heist 2 mods are written in **Lua** and organized into **Modpacks**. A modpack is a folder containing scripts and assets that add new gameplay, actors, and classes to the game. Modpacks can be uploaded to the Steam Workshop and added to your game session through the `Host Game` menu or through the `[ModpackOverride] ModpackList = AbsoluteModpackPath1, AbsoluteModpackPath2` server config setting. Modpacks can also be included in player-created custom maps, ensuring they always run with the map. All scripts are loaded when the team selection begins, and are destroyed after the Round-End UI.

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

Scripts associated with a **BP_LuaActor** — a customizable in-world actor. Each BP_LuaActor has a `LuaFileName` property that links it to its script. Actor scripts define spawning behavior, interactions, and visual setup.

```lua
LogMessage("Loaded MyActor.lua")

-- Initialize when the actor spawns
ListenToEvent("ActorSpawned", function(targetActor)
    if targetActor.LuaFileName == "MyActor.lua" then
        targetActor:SetReplicatedVar("UsesLeft", "3")
    end
end)

-- Client: Show interaction prompt
ListenToEvent("GetInteractName_OnClient", function(targetActor, playerActor)
    if targetActor.LuaFileName == "MyActor.lua" then
        local uses = tonumber(targetActor:GetReplicatedVar("UsesLeft"))
        if uses and uses > 0 then
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
        targetActor.InteractionTimer = 2.0
    end
end)

-- Server: Handle the interaction
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
    "AbilityIcon": "AssassinAbility",
    "AbilityCooldown": 30.0,
    "PassiveName": "Silent Steps",
    "PassiveDescription": "Footsteps make no sound.",
    "PassiveIcon": "SilentStepsIcon",
    "PrimaryWeapon": 1,
    "SecondaryWeapon": 0,
    "ClassCategory": 0
}
```

**Assassin.lua:**
```lua
LogMessage("Loaded Assassin.lua")

-- Client: Ability key pressed
ListenToEvent("AbilityKeyPressed_OnClient", function(playerActor)
    if playerActor.CustomClassString == "Assassin" then
        playerActor:StartAbilityCooldown(30.0)
        playerActor:AbilitySV()
        PlaySound(playerActor, "Woosh.wav", 0.8)
    end
end)

-- Server: Ability execution
ListenToEvent("AbilitySV", function(playerActor)
    if playerActor.CustomClassString == "Assassin" then
        playerActor.Mesh:SetVisibility(false)

        -- Timers require an Actor to run on, like the GameState or, in this case, the playerActor that called AbilitySV
        SetTimer(5.0, "AssassinUncloak", playerActor)
    end
end)

ListenToEvent("AssassinUncloak", function(playerActor)
    playerActor.Mesh:SetVisibility(true)
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
local doors = GetAllActorsOfClass("BP_VaultDoor")

-- By tag
local alarms = GetAllActorsWithTag("AlarmPanel")
local alarm = GetActorWithTag("AlarmPanel")

-- Check if an actor has a specific tag
if ActorHasTag(targetActor, "Interactable") then
    LogMessage("This actor is interactable!")
end

-- All player characters
local players = GetPlayerChars()

-- All controlled pawns (including drones)
local pawns = GetAllControlledPawns()

-- Closest actor of a class to a location
local closest = GetClosestActor("BP_VaultDoor", {X=100, Y=200, Z=0})
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
LogMessage("Health: " .. tostring(player.Health))
LogMessage("Actor: " .. GetActorName(targetActor))
```

Check the logs at: `%APPDATA%/Local/PerfectHeist2/Saved/Logs/PerfectHeist2.log`.
