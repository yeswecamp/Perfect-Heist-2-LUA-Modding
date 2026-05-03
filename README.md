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

Perfect Heist 2 mods are written in **Lua** and organized into **Modpacks**. A modpack is a folder containing scripts and assets that can add custom game logic, new objects with different functions and moving parts, as well as new robber and cop classes to the game.

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

Click on the `Scripts` category button and create a new script. The game generates boilerplate code for you. Click **Edit File** icon to edit the `.lua` file in your preferred text editor (Notepad, VS Code, etc.).

### 3. The Event System

After opening your newly created `.lua` file in your favorite text editor, you will see some basic, pregenerated code.
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

Unreal Engine Actors (players, objects, doors, etc.) are passed to your event callbacks. You can read their variables and call their functions:

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

For AltInteractions (default key: `F`), similar functions and variables are available: `InteractAltSV`, `GetInteractAltName`, and `GetInteractionAltTimer` events and `bCanInteractAlt`, `InteractionAltString`, and `InteractionAltTimmer` variables.

### Custom Class Scripts

Custom classes require **two files** with the same name: a `.json` for basic class data and a `.lua` for ability logic.

List of Weapon IDs: `1=Rifle, 2=SMG, 3=Auto Sniper, 4=Pistol, 5=Rocket Launcher, 6=Shotgun, 7=Grappling Hook, 8=Silenced Pistol, 9=Smoke Launcher, 10=Grenade Launcher, 11=Teargas Launcher, 12=Automatic Pistol, 13=Sniper Rifle, 14=Decoy Launcher, 15=Carbine, 16=Bullpup MP, 17=Tommy Gun, 18=Taser, 19=Sticky Launcher, 20=Heavy Pistol, 21=Modified Pistol, 22=Silenced Rifle, 23=Flash Launcher, 24=Rope Launcher, 25=Syringe Gun, 26=Slug Shotgun, 27=Geiger Counter, 28=Chrono-Nade Launcher, 29=Sceptre, 30=Dagger, 31=Hammer, 32=Sickle, 33=Bottle, 34=Bottle, 35=Gladius, 36=T-Shirt Cannon, 37=Drone Remote, 38=Wrench`

List of Clothing Rows: `Customer_Hoodie_Red, Customer_Jacket_Green, Customer_Hoodie_Black, Customer_Jacket_Red, Employee_PurpleTie, Employee_RedTie, Cook, Cop_1, Cop_2, Cop_3, Cop_4, DEA_Female_1, DEA_Female_2, DEA_Female_3, DEA_Female_4, DEA_Male_1, DEA_Male_2, DEA_Male_3, DEA_Male_4, Spy_Male, Spy_Female`

**Assassin.json:**
```json
{
    "IsRobber": true,
    "DisplayName": "Assassin",
    "ClothingRowName": "Robber_Hoodie_Red",
    "AbilityName": "Cloak",
    "AbilityDescription": "Turn invisible for 5 seconds.",
    "AbilityIcon": "AssassinAbility.png",
    "AbilityCooldown": 30.0,
    "PassiveName": "HP Regeneration",
    "PassiveDescription": "Generates 1 HP every second.",
    "PassiveIcon": "HpRegenerationIcon.png",
    "PrimaryWeapon": 1,
    "SecondaryWeapon": 2,
    "ClassCategory": 0
}
```

`AssassinAbility.png` and `HpRegenerationIcon.png` need to exist in the Modpacks `/Assets/` folder.

**Assassin.lua:**
```lua
LogMessage("Loaded Assassin.lua")

-- PASSIVE: Start HP regeneration when the round starts
ListenToEvent("RoundStarted", function()
    local players = GetPlayerChars()
    for i, player in ipairs(players) do
        if player.CustomClassString == "Assassin" then
            SetTimer(1.0, "AssassinPassiveHeal", player)
            LogMessage("Assassin passive started for " .. GetActorName(player))
        end
    end
end)

-- PASSIVE: Heal 1 HP every second, repeat
ListenToEvent("AssassinPassiveHeal", function(playerActor)
    if playerActor.HP < 100 then
        playerActor.HP = playerActor.HP + 1
    end
    -- Repeat the timer to create a loop
    SetTimer(1.0, "AssassinPassiveHeal", playerActor)
end)

ListenToEvent("AbilityKeyPressed_OnClient", function(playerActor)
    if playerActor.CustomClassString == "Assassin" then
        LogMessage("CLIENT: Assassin cloaking!")

        playerActor:StartAbilityCooldown(6.0)

        -- AbilitySV is called on the client player, but the function executes on the server, which can then handle the logic and replication to all other clients
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

        -- Setting the .preventShooting variable of the player character class to true, so he can't fire while invisible
		playerActor.preventShooting=true

        -- Starting a timer on the playerActor object so he will call LUA back in 5 seconds with the "AssassinUncloak" function
        SetTimer(5.0, "AssassinUncloak", playerActor)
    end
end)

-- When AbilitySV gets called on the server, Ability_ALL gets called for all clients
ListenToEvent("AbilityALL_OnClient", function(playerActor)
    if playerActor.CustomClassString == "Assassin" then
        LogMessage("ALL CLIENTS: Assassin cloaking!")
	
        -- Setting the .Mesh of the playerActor to hidden on all clients. We don't want to set the whole player character hidden, since this logic is getting overwritten by the game code.
        playerActor.Mesh:SetHiddenIngame(true)

        -- Setting his FP_Arms (the first-person view model) to hidden as well, so the player who used the ability can see something happen on his screen for additional feedback
		playerActor.FP_Arms:SetHiddenIngame(true)

        SetTimer(5.0, "AssassinUncloak_ALL", playerActor)
    end
end)

ListenToEvent("AssassinUncloak", function(playerActor)
	playerActor.preventShooting=false
    LogMessage("SERVER: Assassin visible again!")
end)

ListenToEvent("AssassinUncloak_ALL", function(playerActor)
    playerActor.Mesh:SetHiddenIngame(false)
	playerActor.FP_Arms:SetHiddenIngame(false)
    LogMessage("ALL CLIENTS: Assassin visible again!")
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

-- Using FontSize 24 and Custom Color {R=1, G=0, B=0, A=1} for large red text
ShowUIText("Warning", "Low HP!", 0.5, 0.3, 5.0, 24, {R=1, G=0, B=0, A=1})
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

## Actor Components

### Adding Components

You can add any number of Unreal Engine `ActorComponent` components to your custom actors like this:

```lua
local sphere = AddComponent(targetActor, "SphereComponent", "CollisionSphere")
local pointLight = AddComponent(targetActor, "PointLightComponent", "Glow")
```

You can find your spawned components again in different functions by searching for their tag, like `CollisionSphere`:

```lua
local sphere = GetComponentByClass(targetActor, "CollisionSphere")
```

### Visible Meshes

Mesh Components are required for players to see your custom actors. They take in a `.fbx` and a `.png` file from your `/Assets/` folder and can be moved, rotated, and scaled relative to your actor.

```lua
local mesh = AddMeshComponent(targetActor, "Base", "MyMesh.fbx", "MyTexture.png")
mesh:SetRelativeLocation({X=0, Y=0, Z=0})
mesh:SetRelativeRotation({Pitch=0, Yaw=0, Roll=0})
mesh:SetRelativeScale3D({X=1, Y=1, Z=1})
```

### Collision Shapes

Collision Shape Components include `SphereComponent`, `BoxComponent`, and `CapsuleComponent`. They can be used to give your objects invisible and highly efficient collision shapes.

```lua
local sphere = AddComponent(targetActor, "SphereComponent", "Collision")
sphere:SetSphereRadius(50)
sphere:SetCollisionResponseToChannel(CollisionChannel.Pawn, CollisionResponse.Block) -- Block Characters from moving into it. Use CollisionResponse.Ignore to stop blocking characters
sphere:SetCollisionResponseToChannel(CollisionChannel.Visibility, CollisionResponse.Ignore) -- Ignore the visibility channel, meaning bullets can fly through it, and it doesn't get hit by the interaction traces. Set to CollisionResponse.Block if you want players to interact with hit and bullets to hit it
```

Every actor has a `RootComponent`. If you select a Collision Shape as the `RootComponent` for your actor, you can toggle Physics on, and your actor will roll like a ball if you selected the `SphereComponent`, for example.

```lua
SetRootComponent(targetActor, sphere)
sphere:SetSimulatePhysics(true)
sphere:AddForce({X=500, Y=0, Z=100}) -- this needs to be repeated multiple times per second if you want the sphere to continously roll foward
```

### Lights

Light Components include `PointLightComponent`, `SpotLightComponent`, and `RectLightComponent`. They are dynamic lights that can be configured when spawning them, or at any point during the round to change their intensity, range, or color. The `AttenuationRadius` is the setting that affects performance; keep it as low as possible.

```lua
local light = AddComponent(targetActor, "PointLightComponent", "Glow")
light:SetRelativeLocation({X=0, Y=0, Z=200})
light:SetIntensity(50000)
light:SetAttenuationRadius(1000)
light:SetLightColor({R=0, G=255, B=0, A=255})
```

---

## Network Replication

If you need to send specific data like strings or floats *from the local client player* to the server, you can use `SendServerRPC` from the local client's `PlayerChar`.
You can also call `SendServerMulticast` to send data *from the server* to all clients.

```LUA
playerActor:SendServerRPC("MyEvent", "data1", "data2", "data3")
playerActor:SendMulticastRPC("MyEvent", "data1", "data2", "data3")

ListenToEvent("MyEvent", function(playerActor, d1, d2, d3) ... end)         -- server-side
ListenToEvent("MyEvent_OnClient", function(playerActor, d1, d2, d3) ... end) -- client-side
```

If you need to pass along Actor references instead of just basic data, you can use these similar functions:

```LUA
playerActor:SendServerRPCWithActors("MyEvent2", "data1", "data2", targetActor, nil)
playerActor:SendMulticastRPCWithActors("MyEvent2", "data1", "data2", targetActor, nil)

ListenToEvent("MyEvent2", function(playerActor, d1, d2, actor1, actor2) ... end)
ListenToEvent("MyEvent2_OnClient", function(playerActor, d1, d2, actor1, actor2) ... end)
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

Enable `Show Lua Logs in Chat` in the game settings UI or check the logs at: `%APPDATA%/Local/PerfectHeist2/Saved/Logs/PerfectHeist2.log`. 

Or use on-screen HUD messages:

```lua
ShowUIText("DebugLog", "Actor: " .. GetActorName(targetActor), 0.5, 0.1, 3.0)
ShowUIText("DebugLog", "Health: " .. tostring(player.HP), 0.5, 0.15, 3.0)
ShowUIText("DebugLog", "Steam Name: " .. tostring(player.PlayersName), 0.5, 0.2, 3.0)
```


