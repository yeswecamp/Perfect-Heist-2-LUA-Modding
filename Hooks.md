# Hooks Reference

All events that can be listened to with `ListenToEvent`. Each server event also has a `_OnClient` version that fires on clients automatically.

---

## Round Flow Events

### TeamSelectionStarted

Fires when the team selection phase begins.

```lua
ListenToEvent("TeamSelectionStarted", function()
    LogMessage("Pick your team!")
end)
```

### TeamSelectionTick

Fires every tick during the team selection phase.

```lua
ListenToEvent("TeamSelectionTick", function()
    -- Runs every frame during team selection
end)
```

### ClassSelectionStarted

Fires when the class selection phase begins.

```lua
ListenToEvent("ClassSelectionStarted", function()
    LogMessage("Pick your class!")
end)
```

### ClassSelectionTick

Fires every tick during the class selection phase.

```lua
ListenToEvent("ClassSelectionTick", function()
    -- Runs every frame during class selection
end)
```

### RoundStarted

Fires when the gameplay round begins.

```lua
ListenToEvent("RoundStarted", function()
    LogMessage("Round started!")
    local players = GetPlayerChars()
    LogMessage("Player count: " .. #players)
end)
```

### RoundTick

Fires every tick during the active round.

```lua
ListenToEvent("RoundTick", function()
    -- Runs every frame during the round
    -- Use sparingly to avoid performance issues!
end)
```

### RoundRestarted

Fires when the round is restarted.

```lua
ListenToEvent("RoundRestarted", function()
    LogMessage("Round restarted!")
end)
```

---

## Round Finished Events

### RoundFinished

Fires when the round ends, regardless of reason.

```lua
ListenToEvent("RoundFinished", function()
    LogMessage("Round is over!")
end)
```

### RoundFinished_RobberWin

Fires when robbers win the round.

```lua
ListenToEvent("RoundFinished_RobberWin", function()
    LogMessage("Robbers win!")
end)
```

### RoundFinished_CopWin

Fires when cops win the round.

```lua
ListenToEvent("RoundFinished_CopWin", function()
    LogMessage("Cops win!")
end)
```

### RoundFinished_RobsStoleEnough

Fires when robbers win by stealing enough loot.

```lua
ListenToEvent("RoundFinished_RobsStoleEnough", function()
    LogMessage("Robbers stole enough to win!")
end)
```

### RoundFinished_CopsDied

Fires when robbers win because all cops died.

```lua
ListenToEvent("RoundFinished_CopsDied", function()
    LogMessage("All cops are down!")
end)
```

### RoundFinished_RobsDied

Fires when cops win because all robbers died.

```lua
ListenToEvent("RoundFinished_RobsDied", function()
    LogMessage("All robbers are down!")
end)
```

### RoundFinished_CopsAllFired

Fires when robbers win because all cops got fired.

```lua
ListenToEvent("RoundFinished_CopsAllFired", function()
    LogMessage("All cops got fired!")
end)
```

### RoundFinished_TimerOver

Fires when cops win because the round timer expired.

```lua
ListenToEvent("RoundFinished_TimerOver", function()
    LogMessage("Time's up!")
end)
```

---

## Player Events

### AbilityKeyPressed

Fires on the **client** when a player presses the ability key. Use the `_OnClient` version.

| Parameter | Type | Description |
|-----------|------|-------------|
| playerActor | Actor | The player who pressed the ability key |

```lua
ListenToEvent("AbilityKeyPressed_OnClient", function(playerActor)
    if playerActor.CustomClassString == "Assassin" then
        playerActor:StartAbilityCooldown(30.0)
        playerActor:AbilitySV()
        PlaySound(playerActor, "Woosh.wav", 0.8)
    end
end)
```

### AbilitySV

Fires on the **server** when a player's ability is activated via the `AbilitySV()` RPC.

| Parameter | Type | Description |
|-----------|------|-------------|
| playerActor | Actor | The player using the ability |

```lua
ListenToEvent("AbilitySV", function(playerActor)
    if playerActor.CustomClassString == "Assassin" then
        playerActor.Mesh:SetVisibility(false)
        SetTimer(5.0, "AssassinUncloak", playerActor)
    end
end)
```

### AbilityALL

Fires on **all machines** (server and clients) when a player's ability is activated.

| Parameter | Type | Description |
|-----------|------|-------------|
| playerActor | Actor | The player using the ability |

```lua
ListenToEvent("AbilityALL", function(playerActor)
    if playerActor.CustomClassString == "Assassin" then
        PlaySound(playerActor, "CloakSound.wav", 1.0)
    end
end)
```

### PieMenuSelected

Notifies the script that the player has selected on of the pie menu options.

| Parameter | Type | Description |
|-----------|------|-------------|
| playerActor | Actor | The player that spawned the pie menu |
| selectedIndex | Int | The selected Index of the Pie Menu (First Entry = Index 0) |

```lua
ListenToEvent("AbilityKeyPressed_OnClient", function(playerActor)
	if playerActor.CustomClassString == "Assassin" then
        StartPieMenu(playerActor, {
            {Name = "Wall",    Description = "Build a wall",    Icon = "WallIcon.png"},
            {Name = "Floor",   Description = "Build a floor",   Icon = "FloorIcon.png"},
            {Name = "Turret",  Description = "Place a turret",  Icon = "TurretIcon.png"},
            {Name = "Heal",    Description = "Heal nearby",     Icon = "HpRegenerationIcon.png"}
        })
    end
end)

ListenToEvent("PieMenuSelected_OnClient", function(playerActor, selectedIndex)
    if playerActor.CustomClassString == "Assassin" then
        if selectedIndex == 1 then
            LogMessage("Building a wall!")
        elseif selectedIndex == 2 then
            LogMessage("Building a floor!")
        elseif selectedIndex == 3 then
            LogMessage("Placing a turret!")
        elseif selectedIndex == 4 then
            LogMessage("Healing nearby!")
        end
    end
end)
```

### PlayerEnabledFirstPerson

Fires on the local client that changed its player view mode to first-person. Gets called when the player spawns to set up visibility.

| Parameter | Type | Description |
|-----------|------|-------------|
| playerActor | Actor | The player changing his view mode |

### PlayerEnabledThirdPerson

Fires on the local client that changed its player view mode to third-person.

| Parameter | Type | Description |
|-----------|------|-------------|
| playerActor | Actor | The player changing his view mode |

```lua
ListenToEvent("PlayerEnabledFirstPerson_OnClient", function(playerActor)
    LogMessage("Our local player switched to first-person!")
end)
ListenToEvent("PlayerEnabledThirdPerson_OnClient", function(playerActor)
    LogMessage("Our local player switched to third-person!")
end)
```

---

## Damage Events

### PreReceiveDamage

Fires on the **server** right before damage is applied to an actor. Modders can increase the target's HP before damage is subtracted to help them survive.

| Parameter | Type | Description |
|-----------|------|-------------|
| targetActor | Actor | The actor about to receive damage |
| sourceActor | Actor | The actor dealing the damage |
| damage | Float | The amount of damage about to be dealt |
| damageType | Int | The type of damage: 0=Bullet, 1=Explosion, 2=Melee Attack, 3=Fall Damage, 4=Fired, 5=Fire, 6=Poison, 7=HeliRotors, 8=Revived, 9=FiredRespawn, 10=Spikes, 11=Reflection|
| canBeLethal | Bool | Whether this damage can kill the target |

```lua
ListenToEvent("PreReceiveDamage", function(targetActor, sourceActor, damage, damageType, canBeLethal)
    -- Give Assassin extra HP to absorb damage
    if targetActor.CustomClassString == "Assassin" then
        targetActor.Health = targetActor.Health + 20
        LogMessage("Assassin pre-healed 20 HP!")
    end
end)
```

---

## BP_LuaActor Events

### ActorSpawned

Fires on the **server** when a BP_LuaActor spawns in the world.

| Parameter | Type | Description |
|-----------|------|-------------|
| targetActor | Actor | The BP_LuaActor that just spawned |

```lua
ListenToEvent("ActorSpawned", function(targetActor)
    if targetActor.LuaFileName == "HealthStation.lua" then
        targetActor:SetReplicatedVar("UsesLeft", "3")
        AddMeshComponent(targetActor, "Base", "Station.fbx", "Station.png")
    end
end)
```

### GetInteractName

Fires on the **client** when a player looks at an interactable BP_LuaActor. Use the `_OnClient` version. You **must** set `InteractionString` and `bCanInteract` on the target actor.

| Parameter | Type | Description |
|-----------|------|-------------|
| targetActor | Actor | The BP_LuaActor being looked at |
| playerActor | Actor | The player looking at it |

| Must Set | Type | Description |
|----------|------|-------------|
| targetActor.InteractionString | String | The text shown to the player |
| targetActor.bCanInteract | Bool | Whether the player can interact |

```lua
ListenToEvent("GetInteractName_OnClient", function(targetActor, playerActor)
    if targetActor.LuaFileName == "HealthStation.lua" then
        local uses = tonumber(targetActor:GetReplicatedVar("UsesLeft"))
        if uses and uses > 0 then
            targetActor.InteractionString = "Heal (" .. uses .. " left)"
            targetActor.bCanInteract = true
        else
            targetActor.InteractionString = "Empty"
            targetActor.bCanInteract = false
        end
    end
end)
```

### GetInteractionTimer

Fires on the **client** to determine how long an interaction takes. Use the `_OnClient` version. You **must** set `InteractionTimer` on the target actor.

| Parameter | Type | Description |
|-----------|------|-------------|
| targetActor | Actor | The BP_LuaActor being interacted with |
| playerActor | Actor | The player interacting |

| Must Set | Type | Description |
|----------|------|-------------|
| targetActor.InteractionTimer | Float | Seconds the interaction takes (0 = instant) |

```lua
ListenToEvent("GetInteractionTimer_OnClient", function(targetActor, playerActor)
    if targetActor.LuaFileName == "HealthStation.lua" then
        targetActor.InteractionTimer = 2.0
    end
end)
```

### InteractSV

Fires on the **server** when a player completes an interaction with a BP_LuaActor.

| Parameter | Type | Description |
|-----------|------|-------------|
| targetActor | Actor | The BP_LuaActor being interacted with |
| playerActor | Actor | The player who interacted |

```lua
ListenToEvent("InteractSV", function(targetActor, playerActor)
    if targetActor.LuaFileName == "HealthStation.lua" then
        local uses = tonumber(targetActor:GetReplicatedVar("UsesLeft"))
        if uses and uses > 0 then
            targetActor:SetReplicatedVar("UsesLeft", tostring(uses - 1))
            LogMessage(GetActorName(playerActor) .. " healed!")
        end
    end
end)
```

---

## Logic Channel Events

### LogicChannelChanged

Fires on the **server** when a logic channel changes state (e.g. a button activates channel 5).

| Parameter | Type | Description |
|-----------|------|-------------|
| channelID | Int | The logic channel that changed |
| newState | Bool | The new state (`true` = on, `false` = off) |

```lua
ListenToEvent("LogicChannelChanged", function(channelID, newState)
    if channelID == 5 and newState == true then
        LogMessage("Channel 5 activated!")
        local doors = GetAllActorsWithTag("SecretDoor")
        for i, door in ipairs(doors) do
            door:OpenDoor()
        end
    end
end)
```

---

## World Events

### AnyActorSpawned

Fires on the **server** when any gameplay-relevant actor spawns in the world (Blueprint actors and PlayerChars).

| Parameter | Type | Description |
|-----------|------|-------------|
| spawnedActor | Actor | The actor that just spawned |

```lua
ListenToEvent("AnyActorSpawned", function(spawnedActor)
    local className = GetActorClassName(spawnedActor)
    LogMessage("Spawned: " .. className)
end)
```

### AnyActorDestroyed

Fires on the **server** when any gameplay-relevant actor is destroyed.

| Parameter | Type | Description |
|-----------|------|-------------|
| destroyedActor | Actor | The actor being destroyed |

> **Note:** The actor is about to be garbage collected. You can read properties and log, but don't store references to it.

```lua
ListenToEvent("AnyActorDestroyed", function(destroyedActor)
    local className = GetActorClassName(destroyedActor)
    LogMessage("Destroyed: " .. className)
end)
```

---

### PlayerPreInteractSV

Fires on the **server** before a player interacts ("E") with any actor in the world (not just BP_LuaActors).

| Parameter | Type | Description |
|-----------|------|-------------|
| targetActor | Actor | The actor that was interacted with |
| playerActor | Actor | The player who interacted |
```lua
ListenToEvent("PlayerPreInteractSV", function(targetActor, playerActor)
    local className = GetActorClassName(targetActor)
    LogMessage(GetActorName(playerActor) .. " interacted with " .. className)
end)
```

### PlayerInteractedSV

Fires on the **server** after a player interacts ("E") with any actor in the world (not just BP_LuaActors).

| Parameter | Type | Description |
|-----------|------|-------------|
| targetActor | Actor | The actor that was interacted with |
| playerActor | Actor | The player who interacted |
```lua
ListenToEvent("PlayerInteractedSV", function(targetActor, playerActor)
    local className = GetActorClassName(targetActor)
    LogMessage(GetActorName(playerActor) .. " interacted with " .. className)
end)
```

### PlayerAltInteractedSV

Fires on the **server** when a player uses the alternate ("F") interaction on any actor in the world.

| Parameter | Type | Description |
|-----------|------|-------------|
| targetActor | Actor | The actor that was alt-interacted with |
| playerActor | Actor | The player who alt-interacted |
```lua
ListenToEvent("PlayerAltInteractedSV", function(targetActor, playerActor)
    local className = GetActorClassName(targetActor)
    LogMessage(GetActorName(playerActor) .. " alt-interacted with " .. className)
end)
```

### PlayerAiPreInteractSV

Fires on the **server** before a BOT Robber or BOT Cop interacts with any actor in the world (not just BP_LuaActors).

| Parameter | Type | Description |
|-----------|------|-------------|
| targetActor | Actor | The actor that was interacted with |
| playerActor | Actor | The player who interacted |
```lua
ListenToEvent("PlayerAiPreInteractSV", function(targetActor, playerActor)
    local className = GetActorClassName(targetActor)
    LogMessage(GetActorName(playerActor) .. " interacted with " .. className)
end)
```

### PlayerAiInteractedSV

Fires on the **server** after a BOT Robber or BOT Cop interacts with any actor in the world (not just BP_LuaActors).

| Parameter | Type | Description |
|-----------|------|-------------|
| targetActor | Actor | The actor that was interacted with |
| playerActor | Actor | The player who interacted |
```lua
ListenToEvent("PlayerAiInteractedSV", function(targetActor, playerActor)
    local className = GetActorClassName(targetActor)
    LogMessage(GetActorName(playerActor) .. " interacted with " .. className)
end)
```

---

### AllMessage

Fires when a all (not team chat!) chat message is received. This event can run on servers, or on clients if specified with `ListenToEvent("AllMessage_OnClient",`.

| Parameter | Type | Description |
|-----------|------|-------------|
| message | String | The chat message text |
| teamID | Int | The team ID of the sender (0=FromServer, 1=FromRobber, 2=FromCop) |
| playerActor | Actor | The player who sent the message |
```lua
ListenToEvent("AllMessage", function(message, teamID, playerActor)
    LogMessage("Message from " .. GetActorName(playerActor) .. ": " .. message)

    -- Custom chat commands
    if message == "!heal" then
        playerActor.Health = 100
    end
end)
```

To send a message from Lua:
```lua
local gs = GetGameState()
local player = GetPlayerPawn()
gs:AllMessage("Hello from Lua!", 0, player)
```

### TeamMessage

Fires when a team-only chat message is received. This event can run on servers, or on clients if specified with `ListenToEvent("AllMessage_OnClient",`.

| Parameter | Type | Description |
|-----------|------|-------------|
| message | String | The chat message text |
| teamID | Int | The team ID of the sender (0=FromServer, 1=FromRobber, 2=FromCop) |
| playerActor | Actor | The player who sent the message |
```lua
ListenToEvent("TeamMessage", function(message, teamID, playerActor)
    LogMessage("Team Message from " .. GetActorName(playerActor) .. ": " .. message)

    -- Custom chat commands
    if message == "!heal" then
        playerActor.Health = 100
    end
end)
```

---

## Input Events

Fires when a player presses a key locally. Available input keys: `JumpKey`, `InteractKey`, `AltInteractKey`, `AbilityKey`, `CrouchKey`, `ShootKey`, `AdsKey`, `DropKey`

| Parameter | Type | Description |
|-----------|------|-------------|
| PlayerChar | Actor | The local PlayerChar that pressed the key |
| HeistPC | Actor | The local HeistPC that pressed the key  |

```lua
ListenToEvent("JumpKey_OnClient", function(PlayerChar, HeistPC)
    LogMessage("Local Player pressed his Jump Key ")
end)
```

---

## Custom Timer Events

Timer events are created by the modder using `SetTimer`. The event name is whatever string you pass.

```lua
SetTimer(5.0, "MyCustomEvent", someActor)

ListenToEvent("MyCustomEvent", function(actor)
    LogMessage("Timer fired!")
end)
```

---

## Notes

- **Server events** fire without any suffix: `"RoundStarted"`, `"InteractSV"`, `"AbilitySV"`
- **Client events** have `_OnClient` appended automatically: `"GetInteractName_OnClient"`, `"AbilityKeyPressed_OnClient"`
- On **listen servers** and **standalone**, both server and `_OnClient` versions fire automatically
- On **dedicated servers**, only server events fire. Clients only receive `_OnClient` events
- You don't need to manually manage `_OnClient` — the system handles routing based on where the code runs
- **Tick events** (`RoundTick`, `TeamSelectionTick`, `ClassSelectionTick`) fire every frame — use them sparingly to avoid performance issues
