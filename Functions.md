# Functions Reference

All global Lua functions available to modders in Perfect Heist 2.

---

## Event System

### ListenToEvent(eventName, callback)

Register a function to be called when an event fires. See [Hooks.md](Hooks.md) for all available events.

```lua
ListenToEvent("RoundStarted", function()
    LogMessage("Round started!")
end)
```

---

## Logging

### LogMessage(message)

Print a message to the Unreal output log. Useful for debugging.

```lua
LogMessage("Hello from Lua!")
LogMessage("Health: " .. tostring(player.Health))
```

Output appears as: `LUA SCRIPT LOG: Hello from Lua!`

---

## Finding Actors

### GetPlayerChars()

Returns a table of all player character actors in the world, including unpossessed ones (e.g. when a player is flying a drone).

```lua
local players = GetPlayerChars()
for i, player in ipairs(players) do
    LogMessage("Player: " .. GetActorName(player))
end
```

### GetAllControlledPawns()

Returns a table of all currently possessed pawns (player characters, drones, etc.).

```lua
local pawns = GetAllControlledPawns()
for i, pawn in ipairs(pawns) do
    LogMessage("Pawn: " .. GetActorName(pawn))
end
```

### GetAllActorsOfClass(className)

Returns a table of all actors in the world matching the given Blueprint class name. Use the class name without the `_C` suffix.

```lua
local doors = GetAllActorsOfClass("BP_VaultDoor")
for i, door in ipairs(doors) do
    LogMessage("Found door: " .. GetActorName(door))
end
```

### GetClosestActor(className, locationTable)

Returns the closest actor of the given class to a world location.

```lua
local closest = GetClosestActor("BP_VaultDoor", {X=100, Y=200, Z=0})
if closest then
    LogMessage("Nearest door: " .. GetActorName(closest))
end
```

### GetAllActorsWithTag(tag)

Returns a table of all actors that have the specified actor tag.

```lua
local alarms = GetAllActorsWithTag("AlarmPanel")
for i, alarm in ipairs(alarms) do
    LogMessage("Alarm: " .. GetActorName(alarm))
end
```

### GetActorWithTag(tag)

Returns the first actor found with the specified tag. Useful when you know there's only one.

```lua
local alarm = GetActorWithTag("MainAlarm")
if alarm then
    alarm:Activate()
end
```

---

## Actor Info

### GetActorName(actor)

Returns the internal Unreal name of an actor (e.g. `"PlayerChar_C_0"`, `"BP_LuaActor_C_3"`).

```lua
local name = GetActorName(targetActor)
LogMessage("Actor: " .. name)
```

### GetActorClassName(actor)

Returns the Blueprint class name of an actor without the `_C` suffix.

```lua
local className = GetActorClassName(pawn)

if className == "PlayerChar" then
    LogMessage("On foot")
elseif className == "TechDrone" then
    LogMessage("Flying a drone")
end
```

### GetActorTags(actor)

Returns a table of all actor tags as strings.

```lua
local tags = GetActorTags(targetActor)
for i, tag in ipairs(tags) do
    LogMessage("Tag: " .. tag)
end
```

### ActorHasTag(actor, tag)

Returns `true` if the actor has the specified tag.

```lua
if ActorHasTag(targetActor, "Interactable") then
    LogMessage("Can interact!")
end
```

---

### AddActorTag(actor, tag)

Adds a tag to an actor. Does nothing if the tag already exists.
```lua
AddActorTag(targetActor, "Healed")
```

### RemoveActorTag(actor, tag)

Removes a tag from an actor.
```lua
RemoveActorTag(targetActor, "Healed")
```

---

## Game Framework

### GetGameState()

Returns the current GameState actor (HeistGS).

```lua
local gs = GetGameState()
LogMessage("GameState: " .. GetActorName(gs))
```

### GetGameMode()

Returns the current GameMode actor (HeistGM). **Only available on the server.**

```lua
local gm = GetGameMode()
gm:RoundWon_GM(true, 0)
```

### GetPlayerController()

Returns the local player's PlayerController.

```lua
local pc = GetPlayerController()
```

### GetPlayerPawn()

Returns the local player's currently possessed pawn.

```lua
local pawn = GetPlayerPawn()
local className = GetActorClassName(pawn)
LogMessage("Currently controlling: " .. className)
```

> **Note:** `GetPlayerPawn()` and `GetPlayerController()` return the **local** player only. On a dedicated server, this is the first connected player. Use `GetPlayerChars()` or `GetAllControlledPawns()` to get all players.

---

## Timers

### SetTimer(seconds, eventName, actor)

Fires an event after a delay. The actor is passed to the event callback.

```lua
SetTimer(5.0, "MyDelayedEvent", targetActor)

ListenToEvent("MyDelayedEvent", function(actor)
    LogMessage("5 seconds have passed!")
end)
```

Timers are **one-shot** — they fire once and are gone. To repeat, call `SetTimer` again inside the callback.

```lua
ListenToEvent("HeartbeatTick", function(actor)
    LogMessage("Tick!")
    SetTimer(1.0, "HeartbeatTick", actor)
end)

-- Start the loop
SetTimer(1.0, "HeartbeatTick", someActor)
```

---

## Audio

### PlaySound(actor, soundFile, volume)

Plays a sound file from the modpack's `Assets/` folder at the actor's location.

| Parameter | Type | Description |
|-----------|------|-------------|
| actor | Actor | The actor whose location the sound plays at |
| soundFile | String | Filename of the sound (e.g. `"Woosh.wav"`) |
| volume | Float | Volume from 0.0 to 1.0. Optional, defaults to 1.0 |

```lua
PlaySound(playerActor, "Woosh.wav", 0.8)
PlaySound(targetActor, "Explosion.mp3")  -- defaults to volume 1.0
```

Supported formats: `.wav`, `.mp3`

---

## UI

### ShowUIText(identifier, text, x, y, displayTime)

Shows or updates a text element on the player's screen.

| Parameter | Type | Description |
|-----------|------|-------------|
| identifier | String | Unique ID. Reusing an ID updates the existing element |
| text | String | The text to display |
| x | Float | Horizontal position, 0.0 (left) to 1.0 (right). Optional, defaults to 0.5 |
| y | Float | Vertical position, 0.0 (top) to 1.0 (bottom). Optional, defaults to 0.5 |
| displayTime | Float | Seconds before auto-removal. 0 = stays forever. Optional, defaults to 0 |

```lua
-- Temporary message
ShowUIText("Alert", "Alarm triggered!", 0.5, 0.1, 3.0)

-- Persistent HUD element
ShowUIText("Score", "Score: 0", 0.9, 0.05, 0)

-- Update it later
ShowUIText("Score", "Score: 500", 0.9, 0.05, 0)
```

---

## Mesh Components

### AddMeshComponent(actor, componentName, meshFile, textureFile)

Adds a static mesh component to a BP_LuaActor at runtime. Mesh and texture files must be in the modpack's `Assets/` folder.

| Parameter | Type | Description |
|-----------|------|-------------|
| actor | Actor | The BP_LuaActor to add the mesh to |
| componentName | String | A unique name to reference this component later |
| meshFile | String | Filename of the mesh (e.g. `"Base.fbx"`) |
| textureFile | String | Filename of the texture (e.g. `"Base.png"`). Optional, pass `""` for no texture |

```lua
AddMeshComponent(targetActor, "Base", "Station_Base.fbx", "Station_Texture.png")
AddMeshComponent(targetActor, "Screen", "Screen.fbx", "")  -- no texture
```

You can add any number of mesh components to a single actor.

### GetMeshComponent(actor, componentName)

Returns a previously added mesh component by name. You can then call transform and visibility functions on it.

```lua
local base = GetMeshComponent(targetActor, "Base")

base:SetRelativeLocation({X=0, Y=0, Z=50})
base:SetRelativeRotation({Pitch=0, Yaw=90, Roll=0})
base:SetRelativeScale3D({X=2, Y=2, Z=2})
base:SetVisibility(false)
```

---

## Replicated & Local Variables

These are called on actors directly using colon syntax. Available on **BP_LuaActor** and **PlayerChar**.

### actor:SetReplicatedVar(key, value)

Sets a replicated variable on the actor. **Server only.** The value automatically syncs to all clients.

```lua
targetActor:SetReplicatedVar("UsesLeft", "3")
```

### actor:GetReplicatedVar(key)

Reads a replicated variable. Works on both server and client.

```lua
local uses = targetActor:GetReplicatedVar("UsesLeft")
LogMessage("Uses left: " .. uses)
```

### actor:SetLocalVar(key, value)

Sets a local variable that only exists on the current machine. Not replicated.

```lua
targetActor:SetLocalVar("UIHighlighted", "true")
```

### actor:GetLocalVar(key)

Reads a local variable.

```lua
local state = targetActor:GetLocalVar("UIHighlighted")
```

> **Remember:** All values are stored as strings. Use `tonumber()` for math and `tostring()` for storing numbers.
>
> ```lua
> local count = tonumber(actor:GetReplicatedVar("Count"))
> count = count + 1
> actor:SetReplicatedVar("Count", tostring(count))
> ```

---

## Actor Properties & Functions (Reflection)

All wrapped actors support reading Blueprint variables with **dot syntax** and calling Blueprint functions with **colon syntax**.

### Reading Variables

```lua
local health = playerActor.Health
local isRobber = playerActor.IsRobber
local name = playerActor.CustomClassString
```

### Calling Functions

```lua
playerActor:SetActorHiddenInGame(true)
playerActor:StartAbilityCooldown(10.0)
playerActor:AbilitySV()
```

### Accessing Sub-Components

Blueprint component variables return wrapped objects that you can also call functions on:

```lua
local mesh = playerActor.Mesh
mesh:SetVisibility(false)
```

### Passing Vectors and Rotators

Pass `FVector` and `FRotator` values as Lua tables:

```lua
-- FVector
playerActor:SetActorLocation({X=100, Y=200, Z=300}, false, nil, true)

-- FRotator
mesh:SetRelativeRotation({Pitch=0, Yaw=90, Roll=0})
```

### Void Functions Return Nil

Functions that return nothing in Blueprint will return `nil` in Lua. This is normal:

```lua
-- This works, but result will be nil
local result = playerActor:SetActorHiddenInGame(true)
-- Don't check the return value for void functions
```

---

## Helper Functions

### GetFileName(path)

Extracts just the filename from a full file path.

```lua
local name = GetFileName("E:/Mods/MyMod/Scripts/Test.lua")
-- Returns: "Test.lua"
```

### Unwrap(actor)

Extracts the raw UObject from a wrapped actor. You generally don't need this unless you're doing advanced work.

```lua
local raw = Unwrap(wrappedActor)
```

--- 

## Physics Queries

### SphereOverlap(location, radius)

Returns a table of all actors overlapping a sphere at the given location.

| Parameter | Type | Description |
|-----------|------|-------------|
| location | Table | Center point `{X=0, Y=0, Z=0}` |
| radius | Float | Radius of the sphere in units |
```lua
local nearby = SphereOverlap({X=100, Y=200, Z=0}, 500)
for i, actor in ipairs(nearby) do
    LogMessage("Nearby: " .. GetActorName(actor))
end
```

### BoxOverlap(location, extentX, extentY, extentZ)

Returns a table of all actors overlapping a box at the given location.

| Parameter | Type | Description |
|-----------|------|-------------|
| location | Table | Center point `{X=0, Y=0, Z=0}` |
| extentX | Float | Half-size of the box on X axis |
| extentY | Float | Half-size of the box on Y axis |
| extentZ | Float | Half-size of the box on Z axis |
```lua
local inBox = BoxOverlap({X=0, Y=0, Z=100}, 200, 200, 100)
for i, actor in ipairs(inBox) do
    LogMessage("In box: " .. GetActorName(actor))
end
```

### LineMultiTrace(startLocation, endLocation)

Traces a line between two points and returns all actors hit.

| Parameter | Type | Description |
|-----------|------|-------------|
| startLocation | Table | Start point `{X=0, Y=0, Z=0}` |
| endLocation | Table | End point `{X=1000, Y=0, Z=0}` |
```lua
local hits = LineMultiTrace({X=0, Y=0, Z=100}, {X=1000, Y=0, Z=100})
for i, actor in ipairs(hits) do
    LogMessage("Hit: " .. GetActorName(actor))
end
```

### SphereMultiTrace(startLocation, endLocation, radius)

Traces a sphere (thick line) between two points and returns all actors hit.

| Parameter | Type | Description |
|-----------|------|-------------|
| startLocation | Table | Start point `{X=0, Y=0, Z=0}` |
| endLocation | Table | End point `{X=1000, Y=0, Z=0}` |
| radius | Float | Radius of the sphere trace |
```lua
local swept = SphereMultiTrace({X=0, Y=0, Z=100}, {X=1000, Y=0, Z=100}, 50)
for i, actor in ipairs(swept) do
    LogMessage("Swept hit: " .. GetActorName(actor))
end
```

---

## HeistGS Functions

Those functions can be found in [Reflection.md](Reflection.md) as well, but are pretty important, so they will be listed here as well:

### gs:SpawnModLuaActor(fileName, location, rotation, scale, tag)

Spawns a BP_LuaActor with the specified Lua script and properties. If called on the server, the actor will be replicated to all other clients. Moving the actor with SetActorLocation() will also propagate the update to the clients with some basic interpolation.

| Parameter | Type | Description |
|-----------|------|-------------|
| fileName | String | The Lua script filename (e.g. `"HealthStation.lua"`) |
| location | Vector | Spawn location `{X=0, Y=0, Z=0}` |
| rotation | Rotator | Spawn rotation `{Pitch=0, Yaw=0, Roll=0}` |
| scale | Vector | Spawn scale `{X=1, Y=1, Z=1}` |
| tag | String | Actor tag to assign (empty string for none) |
```lua
local gs = GetGameState()
gs:SpawnModLuaActor("HealthStation.lua", {X=500, Y=0, Z=0}, {Pitch=0, Yaw=0, Roll=0}, {X=1, Y=1, Z=1}, "HealStation")
```

Or use the convenience wrapper:
```lua
SpawnLuaActor("HealthStation.lua", {X=500, Y=0, Z=0})
SpawnLuaActor("HealthStation.lua", {X=0, Y=0, Z=0}, nil, {X=2, Y=2, Z=2}, "BigStation")
```

### gs:LuaDestroyActor(fileName, location, rotation, scale, tag)

Destroys a BP_LuaActor matching the given properties. If called on the server, the actor will be destroyed on all clients as well, similarly to how they got updated after spawning the actor through SpawnModLuaActor().

| Parameter | Type | Description |
|-----------|------|-------------|
| fileName | String | The Lua script filename to match |
| location | Vector | Location to match |
| rotation | Rotator | Rotation to match |
| scale | Vector | Scale to match |
| tag | String | Tag to match |
```lua
local gs = GetGameState()
gs:LuaDestroyActor("HealthStation.lua", {X=500, Y=0, Z=0}, {Pitch=0, Yaw=0, Roll=0}, {X=1, Y=1, Z=1}, "HealStation")
```

### gs:LuaSpawnFX(fxName, location, scale)

Spawns a particle effect locally on the current machine.

| Parameter | Type | Description |
|-----------|------|-------------|
| fxName | String | Name of the particle effect |
| location | Vector | World location `{X=0, Y=0, Z=0}` |
| scale | Vector | Scale of the effect `{X=1, Y=1, Z=1}` |
```lua
local gs = GetGameState()
gs:LuaSpawnFX("Explosion", {X=100, Y=200, Z=0}, {X=1, Y=1, Z=1})
```

### gs:LuaSpawnFX_ALL(fxName, location, scale)

Spawns a particle effect on all clients. **Call from server.**

| Parameter | Type | Description |
|-----------|------|-------------|
| fxName | String | Name of the particle effect |
| location | Vector | World location `{X=0, Y=0, Z=0}` |
| scale | Vector | Scale of the effect `{X=1, Y=1, Z=1}` |
```lua
local gs = GetGameState()
gs:LuaSpawnFX_ALL("Explosion", {X=100, Y=200, Z=0}, {X=2, Y=2, Z=2})
```

### gs:LuaSpawnFX_Attached(fxName, location, scale, target)

Spawns a particle effect locally on the current machine.

| Parameter | Type | Description |
|-----------|------|-------------|
| fxName | String | Name of the particle effect |
| location | Vector | World location `{X=0, Y=0, Z=0}` |
| scale | Vector | Scale of the effect `{X=1, Y=1, Z=1}` |
| target | Object | Actor to which this particle will be attached, it will then move with the actor |
```lua
local pawn = GetPlayerPawn()
local gs = GetGameState()
gs:LuaSpawnFX_Attached("Explosion", {X=100, Y=200, Z=0}, {X=1, Y=1, Z=1}, pawn)
```

### gs:LuaSpawnFX_Attached_ALL(fxName, location, scale, target)

Spawns a particle effect attached to on all clients. **Call from server.**

| Parameter | Type | Description |
|-----------|------|-------------|
| fxName | String | Name of the particle effect |
| location | Vector | World location `{X=0, Y=0, Z=0}` |
| scale | Vector | Scale of the effect `{X=1, Y=1, Z=1}` |
| target | Object | Actor to which this particle will be attached, it will then move with the actor |
```lua
local pawn = GetPlayerPawn()
local gs = GetGameState()
gs:LuaSpawnFX_Attached_ALL("Explosion", {X=100, Y=200, Z=0}, {X=2, Y=2, Z=2}, pawn)
```


