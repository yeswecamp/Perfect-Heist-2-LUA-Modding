# Reflection API Reference

This document lists all Blueprint-accessible variables and functions on game classes. This is completely auto-generated so there might be some weird functions or quirky variables in there that don't belong, but it's a lot better than having to guess everything. The game was also not meant to be moddable or shared with multiple developers, so all naming conventions have been violated.

Access these through wrapped actors in Lua, e.g. `playerActor.Health` or `playerActor:SomeFunction()`.

A variable that is marked with `(Replicated)` will automatically propagate its value from the server to all clients, but only if called on the server. Changing their value on a client isn't recommended.


## HeistGS
**Inheritance:** `HeistGS → HeistGameState_CPP → Actor`

### Variables
| Name | Type |
|------|------|
| DefaultSceneRoot | Object |
| hackedPCs | Int |
| roundLive? | Bool (Replicated) |
| TeamSelecTimer | uint8 (Replicated) |
| ClassSelecTimer | uint8 (Replicated) |
| savedMoney | Int (Replicated) |
| requiredSavedMoney | Int (Replicated) |
| copRespawns | Int (Replicated) |
| RoundTimer | Int (Replicated) |
| RoundTimerSV | FTimerHandle |
| noSprinting? | Bool (Replicated) |
| copsInfRespawns? | Bool (Replicated) |
| useSprintingStamina? | Bool (Replicated) |
| useOvertime? | Bool (Replicated) |
| currentlyOT? | Bool (Replicated) |
| otRoundtime | Float |
| OvertimeTimerSV | FTimerHandle |
| ignoreTeamLimits? | Bool (Replicated) |
| copPercentage | Float (Replicated) |
| copCarRifles | Int (Replicated) |
| allowTP? | Bool (Replicated) |
| cryptoPCs | Int |
| remainingRobberRespawns | Int (Replicated) |
| onlyFishyKills | Bool (Replicated) |
| chairmanbattle | Bool (Replicated) |
| aliveVIPs | Int (Replicated) |
| robbersHaveHitman | Bool (Replicated) |
| allowSpectators? | Bool (Replicated) |
| allowTeamDmg? | Bool (Replicated) |
| SteamWorkshopID | FSteamUGCItemId |
| extraSMs | Object |
| MapStartTime | FDateTime |
| CustomMapFilePath | String |
| loadingMap? | Bool |
| meshRows | TMap |
| LeDataC | TMap |
| directionalVC? | Bool (Replicated) |
| respawnTimeCops | Int (Replicated) |
| respawnTimeRobs | Int (Replicated) |
| sortedRobSpawns | Array |
| customMapDeletedActs | Array |
| customMapDeletedActsString | String |
| allowedClassGroups | Array (Replicated) |
| aliveCrowns | Int (Replicated) |
| onDedicatedServer? | Bool (Replicated) |
| dediServerCustomMaps | Array (Replicated) |
| unranked? | Bool (Replicated) |
| serverFPS | Int (Replicated) |
| customTextureCache | TMap |
| PickPhaseType | TEnumAsByte<PickPhaseType> (Replicated) |
| bannedRobs | Array (Replicated) |
| bannedCops | Array (Replicated) |
| inBanPhase? | Bool (Replicated) |
| inClassSelec? | Bool (Replicated) |
| onEmptyMap? | Bool |
| foundCustomMapSublevel? | Bool |
| loadedSublevels | Array |
| loadingSublevel | Bool |
| serverOwnerID | String (Replicated) |
| fullServerSettings | Array (Replicated) |
| snowy? | Bool |
| LuaTickTimer | FTimerHandle |
| customClasses | Array (Replicated) |
| customClassesMap | TMap |
| allClassesMap | TMap |
| RuntimeAudioImporter | Object |
| soundFilesToLoad | Array |
| serverNeedsToReloadLuaAssets | Bool |
| LuaWidgets | TMap |
| LuaTextures | TMap |
| LuaMeshFilePaths | TMap |
| currentMapLoadLine | String |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| RestartCl | none | bool |
| RestartSV | CallFunc_GetGameInstance_ReturnValue: UGameInstance*, K2Node_DynamicCast_AsHeist_GI: UHeistGI_C*, K2Node_DynamicCast_bSuccess: bool | bool |
| getRobberSpawns | CallFunc_sortRobberSpawns_out: TArray, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Greater_IntInt_ReturnValue: bool | TArray |
| PlayModSound | SoundPath: FString, Location: FVector, Volume: float | void |
| LoadLuaSounds | soundFIles: TArray | void |
| HandleLUA_SV | none | void |
| LuaTeamTimer | none | void |
| LuaHandleRoundWon | robbersWon?: bool, WonReason: TEnumAsByte<RoundWonEnum> | void |
| LuaClassSelectionStart | none | void |
| LuaRoundStart | none | void |
| LuaClassTick | none | void |
| LuaRoundTick | none | void |
| LuaTeamSelectionStarted | none | void |
| ResetLuaALL | none | void |
| LoadLuaAssets | paths: TArray | void |
| ShowModUIText | Identifier: FString, DisplayText: FString, X: float, Y: float, DisplayTime: float | void |
| RemoveAllLuaWidgets | none | void |
| LoadLuaMeshes | sourceFiles: TArray | void |
| LoadLuaTextures | sourceFiles: TArray | void |
| SpawnModLuaActor | Target: Object | void |
| LuaDestroyActor | LuaFileName: FString, Location: FVector, Rotation: FRotator, Scale: FVector, Tag: FString | void |
| TeamMessage | Message: FString, TeamID: uint8, char: APlayerChar_C* | void |
| AllMessage | String: FString, TeamID: uint8 (0=FromServer, 1=FromRobber, 2=FromCop), char: APlayerChar_C* | void |
| StartRoundTimerSV | none | void |
| StartSetRoundTimer | none | void |
| SetRoundTimer | none | void |
| RoundTimerEnded | none | void |
| UpdateGiValues | none | void |
| OvertimeTimeout | none | void |
| UpdateVIPs | none | void |
| SpawnMapSV | FullFilePath: FString | void |
| LoadMapFromFolder | FullFilePath: FString | void |
| AddLoadingScreenAll | none | void |
| UndeleteActor | actor: AActor* | void |
| EinsteinTimeDelayer | none | void |
| UpdateCrowns | none | void |
| ClearCustomTextureCache | none | void |
| LoadSublevel | LevelName: FName, reason: FString | void |

---

## HeistGM
**Inheritance:** `HeistGM → GameModeBase → Info → Actor`

### Variables
| Name | Type |
|------|------|
| DefaultSceneRoot | Object |
| Inwaiting? | Bool |
| TeammakingTimer | FTimerHandle |
| inTeamMaking? | Bool |
| inSelection? | Bool |
| SelecTimer | FTimerHandle |
| SpawnX | Float |
| SpawnY | Float |
| CopSpawnPoint | Object |
| RobSpawnPoints | Array |
| RoundLive? | Bool |
| dontDoRoundStartMenus | Bool |
| deleteClasses | Array |
| Name | String |
| Password | String |
| InsiderSpawnPoint | Object |
| AgentSpawnPoint | Object |
| spawnOffset | FVector |
| MapDisplayName | String |
| spottedRobberItems | Array |
| bannedIDs | Array |
| diedThisRounds | Array |
| nextRoundMaxMoney | Int |
| serverOwner | FBPUniqueNetId |
| noTeamDmg? | Bool |
| spawnPointHelper | Object |
| spawnedRobberMoneyBags | Int |
| ServerOwnerString | String |
| horseSpawn | Object |
| copspawns | Array |
| TargetMap | String |
| TargetMapSteamID | FSteamUGCItemId |
| needsMapSwitch | Bool |
| workshopFolderPath | String |
| workshopMapNameToID | TMap |
| isMapSwitching? | Bool |
| inBanPhase | Bool |
| bannedRobs | Array |
| bannedCops | Array |
| classOrderForBanPhase | Array |
| pickPhaseTypes | Array |
| pickPhaseItr | Int |
| LuaTickTimer | FTimerHandle |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| LoginWhileTeamSelection | Target: AController*, CallFunc_K2_GetPawn_ReturnValue: APawn*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool | void |
| WaitingForPlayers | none | void |
| RestartHeistGame | none | void |
| StartWaitingTick | none | void |
| TeamMakingFinished | none | void |
| DeleteStuff | none | void |
| TellPlayersTeammakingStarts | none | void |
| Post_TeamSelection | none | void |
| RestartStuff | none | void |
| EndSelection | none | void |
| TellPlayersSelectionEnded | none | void |
| CheckReadys | none | void |
| StartCheckReadyTick | none | void |
| GetSpawnPoints | none | void |
| RespawnPlayers | none | void |
| RespawnPlayer | Target: APlayerChar_C*, randomSpawn?: bool | void |
| Timer | none | void |
| SpawnExtraBombBags | none | void |
| PostCharSelecStuff | none | void |
| SetPlayerWeps | none | void |
| RoundWon_GM | robbersWon?: bool, wonReason: TEnumAsByte<RoundWonEnum> | void |
| UpdateSession | none | void |
| CreateSession | none | void |
| StartUpdateSession | none | void |
| StartFpsTimer | none | void |
| PrintFPS | none | void |
| K2_OnLogout | ExitingController: AController* | void |
| SpawnAnimals | none | void |
| K2_PostLogin | NewPlayer: APlayerController* | void |
| KickPlayer | player: APlayerChar_C*, noban?: bool, steamIdToBan: FBPUniqueNetId | void |
| SpawnDrillBags | none | void |
| SpawnArmsDealerMoney | none | void |
| SpawnChairmanEvent | none | void |
| SpawnVipCheck | none | void |
| SpawnExtraClothesBags | none | void |
| SetMaxPlayers | none | void |
| SpawnMasterthiefDiamonds | none | void |
| ExecuteMapSwitch | none | void |
| RoundstartSpawnProtection | none | void |
| SpawnActorFans | none | void |
| SpawnQueenCrowns | none | void |
| SpawnRumBags | none | void |
| DS_GetInstalledMaps | none | void |
| DisplayServerMOTD | none | void |
| UpdateBannedClasses | none | void |
| TeamMakingTimerFinished | none | void |
| TemporarilyBanSteamID | steamID: FBPUniqueNetId | void |

---


## Destroyable_Base
**Inheritance:** `Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| DefaultSceneRoot | Object |
| HP | Float |
| MinDamage | Float |
| ExplosionSound | Object |
| ExplosionScale | FVector |
| ExplosionFX | Object |
| ExplosionRelativeOffset | FVector |
| blockbullets? | Bool |
| longexplosion? | Bool |
| dontExplode? | Bool |
| noMeleeDmg? | Bool |
| canHeliDmg? | Bool |
| bulletMulti | Float |
| scrapClass | Object |
| pickedUp? | Bool |
| bonusDmgAroundCenter? | Bool |
| center | FVector |
| centerDmgMulti | Float |
| centerRadius | Float |
| copDestroyed? | Bool |
| belongsToCops? | Bool |
| scrapScale | FVector |
| scrapOffset | FVector |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| CanBePenetrated? | inputDmg: float | float |
| bulletsCanDmg? | helper: bool, blockbulletdmg?: bool | bool |
| destroyedCl | none | void |
| DmgHook | none | void |

---

## PlayerChar
**Inheritance:** `PlayerChar → MyCharacter → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| VoipAudioLOUD | Object |
| VoipAudioQUIET | Object |
| VoipAudioMEDIUM | Object |
| FP_WeaponWidget | Object |
| RumBag | Object |
| AdsShield | Object |
| FP_Barrel | Object |
| BarrelScene | Object |
| SK_SkelTemp | Object |
| XRayPP | Object |
| ActionComponent1 | Object |
| FX_Invincible | Object |
| RevivesBag | Object |
| vest | Object |
| FX_ConfusedSmoke | Object |
| DrillBag | Object |
| ShieldBoxingCaps | Object |
| shieldcol1 | Object |
| SM_Prop_Microwave_Door_Glass_06 | Object |
| SM_Prop_Microwave_Door_Glass_05 | Object |
| RiotShieldBackTP | Object |
| SM_Prop_Microwave_Door_Glass_04 | Object |
| SM_Prop_Microwave_Door_Glass_03 | Object |
| SM_Prop_Microwave_Door_Glass_02 | Object |
| SM_Prop_Microwave_Door_Glass_01 | Object |
| shieldcol | Object |
| RiotShieldFP | Object |
| RiotShieldTP | Object |
| Decal | Object |
| MaskTP | Object |
| Niagara | Object |
| StaticMesh2 | Object |
| FX_PoisonedSmoke | Object |
| FP_Hammer | Object |
| rope | Object |
| jetpackFX | Object |
| FX_HealSmoke | Object |
| HairTP | Object |
| ScanVisPP | Object |
| FootprintComponent | Object |
| teamnameWidget | Object |
| BoxingCaps | Object |
| notDisguisedWidget | Object |
| BombBag | Object |
| MoneyFX | Object |
| MoneyBag | Object |
| NinjaCardboardBox | Object |
| ThermalVisPP | Object |
| HeadHitbox | Object |
| DeadBodyDrop | Object |
| DeadBody | Object |
| TP_Hook | Object |
| TP_Cable | Object |
| FP_Hook | Object |
| FP_Cable | Object |
| WeaponComponent | Object |
| Tp_MuzzleFlashLight | Object |
| Tp_MuzzleEnd | Object |
| TP_Weapon | Object |
| MuzzleFlashLight | Object |
| FP_MuzzleEnd | Object |
| SceneCaptureComponent2D | Object |
| FP_Arms | Object |
| SpringArm | Object |
| FP_Scope | Object |
| FP_Mag | Object |
| FP_Slider | Object |
| FP_Weapon | Object |
| Camera | Object |
| PitchSV | Float (Replicated) |
| OldYaw | Float |
| YawChangeAvg | Float |
| CurrentZone | TEnumAsByte<ZoneEnum> |
| onLadder? | Bool |
| MeshSv | Object (Replicated) |
| PlayerHUD | Object |
| robber? | Bool (Replicated) |
| HP | Float (Replicated) |
| ClassID | uint8 (Replicated) RobberClasses: 1=Insider, 2=Heavy, 3=Tech, 4=Demo, 5=Ninja, 6=Sniper, 7=Agent, 8=Doctor, 9=Distractor, 10=Scout, 11=Engineer, 12=Madman, 13=Geek, 14=Poison, 15=Mafia Boss, 16=Mechanic, 17=Crypto, 18=Arms Dealer, 19=Pickpocket, 20=FED Chairman, 21=Vault Cracker, 22=Joker, 23=Hitman, 24=Micro, 25=Gym Buddy, 26=Master Thief, 27=Actor, 28=Albert Einstein, 29=Karl Marx, 30=Al Capone, 31=Artist, 32=Deaddrop. --- CopClasses: 1=Officer, 2=Spy, 3=Swat, 4=FBI, 5=Riot Control, 6=Detective, 7=Combat Medic, 8=Sergeant, 9=Cyber Police, 10=Hornet, 11=Developer, 12=Manager, 13=Sheriff, 14=Firefighter, 15=Reinforcer, 16=Inventor, 17=FED Agent, 18=Vigil, 19=Traffic Cop, 20=FED Chairman, 21=Backup, 22=Bodyguard, 23=Pilot, 24=Janitor, 25=Canine, 26=Marie Curie, 27=Queen Elizabeth, 28=Julius Caesar, 29=Surge, 30=Swarm (Drones), 31=Swarm. |
| MeshMatSv | Object (Replicated) |
| RemainingInteractTimer | Float |
| InteractObjWithTimer | Object |
| hasTeam? | Bool (Replicated) |
| ready? | Bool (Replicated) |
| inSelection? | Bool |
| BlockInput? | Bool |
| ClassSelecWidget | Object |
| TeamSelecWidget | Object |
| PlayersName | String (Replicated) |
| dead? | Bool (Replicated) |
| HudChar | Object |
| RespawnWidget | Object |
| RespawnTimer | FTimerHandle |
| CurrentlySpectatingHim | Object |
| MeshZone | TEnumAsByte<ZoneEnum> |
| pingCount | Int |
| autop? | Bool |
| randomAP | Int |
| spectating? | Bool |
| RespawnTimerCl | FTimerHandle |
| SprintKeyDown? | Bool |
| DeathInfo | FDeathInfo__pf1458230002 (Replicated) |
| Avatar | Object |
| SpectatorWidget | Object |
| Stamina | Float |
| WonRounds | Int (Replicated) |
| vestHP | Float (Replicated) |
| scoutJumpDown? | Bool |
| usedHornetJump | Int |
| spawnprotect? | Bool (Replicated) |
| ForceHidden? | Bool (Replicated) |
| ridingThisVehicle | Object |
| roped? | Bool (Replicated) |
| RobberSpawnID | uint8 (Replicated) |
| playerStateAlways | Object (Replicated) |
| CollisionEnabledSV | Bool (Replicated) |
| KillfeedWidget | Object |
| tasered? | Bool (Replicated) |
| recentlyFireDmg? | Bool |
| AltInteractObjTimer | Object |
| thirdPerson? | Bool |
| UniqueNetID | FBPUniqueNetId |
| selectedMask | Int (Replicated) |
| maskOn? | Bool (Replicated) |
| painted? | Bool (Replicated) |
| currentClassRank | Int (Replicated) |
| hitotherplayerrecently? | Bool |
| deathLoc | FVector |
| wasInSelec? | Bool |
| playersHeDmgedThisRound | TMap |
| playersHeShotThisRound | TMap |
| lsd | Object |
| oldLoc | FVector |
| uncuffTimer | FTimerHandle |
| prevDeathInfo | FDeathInfo__pf1458230002 |
| uncuffed? | Bool |
| spectator? | Bool (Replicated) |
| onlySpectateCops? | Bool (Replicated) |
| onIce? | Bool |
| clan | FBPSteamGroupInfo (Replicated) |
| trampIncVel | Float |
| VOIP_Talker | Object |
| talking? | Bool (Replicated) |
| dropStartTimer | Float |
| ActionComponent | Object |
| spawnProtectStart | FDateTime |
| deadNoRespawns | Bool |
| lastDmgedTime | Float |
| currentAreaName | String |
| waitingForRespawn? | Bool |
| jumpChargeTimeDown | Float |
| chargingJump | Bool |
| highScore | Int |
| hiddenLoc | FVector (Replicated) |
| interactTimerOnStart | Float |
| BanPhaseWidget | Object |
| bannedClasses | Array (Replicated) |
| currentPickPhase | TEnumAsByte<PickPhaseType> |
| currentClassRow | FClassesStruct__pf1489439355 |
| outlineAct | Object |
| recentlyDamagedByDog? | Object |
| traceHitCommponent | Object |
| CustomClassString | String (Replicated) |
| preventShooting | Bool (Replicated) |
| ReplicatedVars | Array (Replicated) |
| LocalVars | Array |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetRadiation | loc: FVector | float |
| Taser | secs: float | bool |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C*, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_SelectFloat_ReturnValue: float, CallFunc_SelectFloat_ReturnValue_1: float | bool |
| RestartCl | none | bool |
| RestartSV | none | bool |
| ToggleThermal | on?: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| bulletsCanDmg? | helper: bool | bool |
| SetClass | classID: uint8 | void |
| isClass | robber: bool, classID: uint8, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_EqualEqual_BoolBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | bool |
| sameTeam? | other: APlayerChar_C*, CallFunc_EqualEqual_BoolBool_ReturnValue: bool, CallFunc_EqualEqual_BoolBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool | bool |
| isClass? | rob?: bool, id: uint8, CallFunc_EqualEqual_BoolBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | bool |
| HealPlayer | amount: float, CallFunc_HasAuthority_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FMax_ReturnValue: float, CallFunc_FMin_ReturnValue: float | void |
| AbilitySV | none | void |
| StartAbilityCooldown | secs: float | void |
| AbilityMulticast | none | void |
| SetFpTpVis | none | void |
| StartPitchRepl | none | void |
| PitchReplTick | none | void |
| PitchReplSV | Pitch: float | void |
| CheckTurnAnim | none | void |
| InitHUD | none | void |
| InteractOnSV | Target: AActor* | void |
| InteractAltSV | Target: AActor* | void |
| InteractTick | none | void |
| InteractTickStart | none | void |
| StartSprintSV | none | void |
| StopSprintSV | none | void |
| ForceTP | none | void |
| StartSelectionMenuCl | none | void |
| StartTeammakingMenuCl | none | void |
| SelectionEndedMidLogin | none | void |
| ClassSelectionEnded | none | void |
| WantsToTeam | rob?: bool, hasTeam?: bool | void |
| WantsToTeamSV | rob?: bool, hasTeam?: bool | void |
| UpdateClassCl | ClassID: uint8, customClass: FString | void |
| UpdateClassSV | ClassID: uint8, force?: bool, rank: int32, dontRespawn: bool, customClass: FString | void |
| SetReadyCl | ready?: bool | void |
| SetReadySV | ready?: bool | void |
| DrawSelectionHUD | none | void |
| ResetVarsCl | none | void |
| DrawTeammakingHUD | none | void |
| FocusOnSelectionWidget | none | void |
| GetHudChar | none | void |
| PostCharSelecORRespawnCl | none | void |
| ResetVarsSV | none | void |
| PlayerDiedCl | killer: APlayerChar_C*, dmgToKiller: float, shotsToKiller: int32 | void |
| PlayerRespawnedCl | none | void |
| PlayerDiedSv | none | void |
| PlayerRespawnedSv | none | void |
| PlayerDiedSvNoRespawn | fired?: bool, noRagdoll?: bool | void |
| StartSpectatingCl | fired?: bool | void |
| SpawnPingSV | Loc: FVector, PingID: int32 | void |
| SpawnPingCl | Loc: FVector, PingID: int32 | void |
| ChangeSpectating | none | void |
| ChangeSpectatingMinus | none | void |
| ActivateNotDisguisedWidget | none | void |
| TickTeamName | none | void |
| GetNameSV | none | void |
| GotShotCl | Source: AActor* | void |
| TellClToDisplayAlert | alert: FString, explaination: FString, secs: float | void |
| GetSteamIcon | none | void |
| OnLanded | Hit: FHitResult | void |
| CheckOwnKillfeed | none | void |
| StopSpectating | none | void |
| StaminaTick | none | void |
| StartSprint | none | void |
| StopSprint | none | void |
| ForceStartSprint | none | void |
| SupriseRespawnSV | loc: FVector, HP: float | void |
| SupriseRespawnCl | none | void |
| ResetVarsClMidround | none | void |
| MonitoredChecked | none | void |
| SetWonRoundsSV | WonRounds: int32 | void |
| ScoutJumpLoop | none | void |
| StartScoutJumpLoop | none | void |
| SpectatingTIck | none | void |
| TellSvCurrSpec | spec: AActor* | void |
| HornetJumpedCl | none | void |
| HornetJumpedSV | none | void |
| HornetJumpedAll | none | void |
| RespawnProtectSV | none | void |
| TellClPossessed | Z: float | void |
| FallingFix | none | void |
| IncreasePingCount | none | void |
| InterruptRespawnCauseFiredSV | none | void |
| InterruptRespawnCauseFiredCl | none | void |
| UncuffCl | none | void |
| UncuffSV | none | void |
| SetRobSpawnIDCl | id: uint8 | void |
| SetRobSpawnIdSV | id: uint8 | void |
| RetryInteract | none | void |
| CopSupriseRespawnedCl | none | void |
| GotShotClNoSlow | Source: AActor* | void |
| TaseredSV | Duration: float | void |
| TaseredCl | none | void |
| SupriseRespawnAll | none | void |
| RecentlyFireDmgSV | none | void |
| PlayInteractBeepCl | none | void |
| SetMaskSV | selectedMask: int32 | void |
| SetMaskCl | selectedMask: int32 | void |
| SetMaskOnSv | maskOn?: bool | void |
| StartAmmoMenu | none | void |
| RemoveMaskCL | none | void |
| UpdateClassRankSV | classid: uint8, rank: int32, robber: bool | void |
| HitOtherPlayerRecently | none | void |
| DisplayPlayerKillerInfo | killer: APlayerChar_C*, dmgToKiller: float, shotsToKiller: int32 | void |
| OnJumped | none | void |
| PoisenedJokerCl | none | void |
| DealDmgSV | Damage: float, Source: AActor*, DmgType: TEnumAsByte<DamageType> | void |
| HandleVisTick | none | void |
| StartAfkCheck | none | void |
| checkAFK | none | void |
| Uncuff | none | void |
| CuffTick | none | void |
| MaskEquipSound | none | void |
| LadderTick | none | void |
| TryJoinSpecSV | onlyCops?: bool | void |
| StartSelecSpectators | none | void |
| InitClan | none | void |
| SetClanSV | clan: FBPSteamGroupInfo | void |
| ForceControlRotCl | z: float | void |
| ToggleSprinting | none | void |
| PlayerPressedRespawnSV | none | void |
| EndSpawnProtect | none | void |
| RecheckSpawnProtect | none | void |
| AFK_Kick | none | void |
| IgnoreServerCorrectionsSV | secs: float | void |
| LaunchCharacterClient | LaunchVelocity: FVector | void |
| LaunchCharacterSV | LaunchVelocity: FVector | void |
| SpawnBulletReflectionALL | Spawn Transform Location: FVector, Spawn Transform Rotation: FRotator | void |
| StartTigerMaskCharge | none | void |
| RetryAltInteract | none | void |
| ForceHiddenTick | none | void |
| StartBanPhaseMenuCL | pickPhaseType: TEnumAsByte<PickPhaseType> | void |
| SetBannedClassSV | ban: uint8 | void |
| SetOutlineToActor | act: AActor* | void |
| RecentlyAttackedByDog | dog: APolice_Dog_C* | void |
| LuaTestPrint | none | void |

---

# Components

Access components through their parent actor, e.g. `playerActor.WeaponComponent.CurrentWeaponID`

## WeaponComponent (Component)

### Variables
| Name | Type |
|------|------|
| CurrentWeaponID | uint8 (Replicated) |
| shootingCl? | Bool |
| shootingSV | Bool |
| FP_Weapon | Object |
| FP_Mag | Object |
| FP_Slider | Object |
| FP_Barrel | Object |
| FP_Arms | Object |
| FP_Scope | Object |
| MuzzleEnd | Object |
| MuzzleFlashLight | Object |
| adsCl? | Bool |
| TP_Weapon | Object |
| Tp_MuzzleEnd | Object |
| PlayerChar | Object |
| Mesh | Object |
| Camera | Object |
| Tp_MuzzleFlashLight | Object |
| reloadingCl? | Bool |
| CurrentAmmo | Array |
| ReserveAmmo | Array |
| EquippedWeapons | Array |
| reloadingSV? | Bool (Replicated) |
| currentRecoilMulti | Float |
| recentlyFired? | Bool |
| HookCableAct | Object |
| EquippedSkins | Array (Replicated) |
| HookTargetLoc | FVector |
| GrappleHitPoint | Object (Replicated) |
| LastHookVel | FVector |
| Hud_Character | Object |
| NoDecalClasses | Array |
| BloodClasses | Array |
| pullingOutWep? | Bool |
| needstoPullOutWep? | Bool |
| LastEquippedSlot | uint8 |
| CurrentInacc | Float |
| CurrentInaccMovPart | Float |
| CurrentSlot | uint8 |
| isBoxing? | Bool |
| SelectedScopes | Array |
| SprintRecoveryTimer | FTimerHandle |
| CurrentWepRow | FWeaponTypesStructs__pf3747386746 |
| adsButtonDown? | Bool |
| FpShootAnimMont | Object |
| FinishFracReloadTimer | FTimerHandle |
| reloadingAnimPlaying? | Bool |
| inspecting? | Bool |
| FP_Hammer | Object |
| heat | Float |
| extendedMags? | Bool |
| WepSwaps | TMap |
| AmmoWidget | Object |
| NextAmmoType | Int |
| CurrentAmmoType | Int (Replicated) |
| boxhit? | Bool |
| lastEquippedWep | uint8 |
| recentlyHooked? | Bool |
| lastSwappedToSlot | uint8 |
| remainingHookJumps | Int |
| LocalRadiation | Float |
| BarrelScene | Object |
| MeleeHitTimer | FTimerHandle |
| adsMelee? | Bool (Replicated) |
| skipNextAnimRefresh | Bool |
| crosshairHint | FText |
| inputBuffersSinceLastInput? | Int |
| SwarmDronePreview | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| PlayFireAnimHUD | CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_IsValid_ReturnValue: bool, CallFunc_Array_Get_Item: AHUD_Character_C* | void |
| UpdateFpWeaponModel | skipPullout?: bool | void |
| EquipWeaponFromSlotSV | SlotID: uint8 | void |
| StartShootingSV | none | void |
| StopShootingSV | none | void |
| ShootKeyClicked | bufferedInput?: bool | void |
| ShootKeyUnclicked | none | void |
| Shoot_TickCl | none | void |
| FireBulletCl | Randomness: float | void |
| Shoot_TickClStart | none | void |
| FireBulletClTP | Randomness: float | void |
| Shoot_TickClTP | none | void |
| Shoot_TickClStartTP | none | void |
| FireRocketSV | StartLoc: FVector, Rot: FRotator | void |
| FireRocketCl | TargetLoc: FVector, Rot: FRotator | void |
| HitShotSV | Target: FVector, HitActor: AActor* | void |
| PlayShotFpFX | none | void |
| SpawnBulletClTP | TargetLoc: FVector | void |
| InitComponents | none | void |
| ADS_Enable | none | void |
| ADS_Disable | force: bool | void |
| UpdateFOV | none | void |
| StartReloadCl | evenIfMagFull?: bool, fromFractionReload?: bool | void |
| InitStartingAmmo | none | void |
| ReloadSuccessfull | none | void |
| ReloadCancelled | none | void |
| StartReloadSV | none | void |
| StopReloadSV | none | void |
| UpdateMagVis | none | void |
| HandleShotFP | TargetLoc: FVector, hit?: bool, hitAct: AActor* | void |
| ShotTpFX | none | void |
| RemoveRecoilTick | none | void |
| RecentlyFiredShot | none | void |
| FireHookCl | Loc: FVector, hitAct: AActor* | void |
| FireHookSV | Loc: FVector | void |
| UpdateHook | none | void |
| DestroyHook | reason: FString | void |
| JumpWhileHooked | none | void |
| DestroyHookSV | none | void |
| JumpAfterhookSV | none | void |
| ReloadAnimTP | none | void |
| FireGrenadeSV | rot: FRotator | void |
| FireGrenadeCl | TargetLoc: FVector | void |
| FireHeavyGrenadeSV | rot: FRotator, loc: FVector | void |
| FireHeavyGrenadeCl | TargetLoc: FVector | void |
| FireTeargasSV | rot: FRotator, loc: FVector | void |
| FireTeargasCl | TargetLoc: FVector | void |
| GainReserveAmmoForAllWeps | none | void |
| EquipWeaponFromSlotCl | SlotID: uint8, neverSwap?: bool | void |
| HitShotSv2 | local: FVector, HitActor: AActor* | void |
| CheckBoxingSV | none | void |
| CheckBoxingFP | none | void |
| StartBoxingBool | none | void |
| StopBoxingFP | none | void |
| ForceStopSprintingTemporarily | none | void |
| CanSprintAgainAfterShot | none | void |
| FinishFracReloadingAnim | none | void |
| RocketAll | Rot: FRotator, StartLoc: FVector | void |
| HitShotPen | local: FVector, HitActor: AActor*, dmg: float, penact: AActor* | void |
| FireDecoyGrenadeSV | rot: FRotator, loc: FVector | void |
| FireDecoyGrenadeCl | TargetLoc: FVector | void |
| SetSkinSv | WepID: uint8, SkinID: uint8 | void |
| ResetCl | none | void |
| AddWepToLastSlot | WeaponID: uint8 | void |
| AddWepToSlotSV | slot: uint8, WeaponID: uint8 | void |
| StartInspecting | none | void |
| StopInspecting | none | void |
| HeatTick | none | void |
| LoadSkins | none | void |
| SetSkinsArraySV | skins: TArray | void |
| FireTaserCl | none | void |
| SpawnTaserCl | target: FVector, hit: AActor* | void |
| SpawnTaserSV | target: FVector, hit: AActor* | void |
| SpawnTaserAll | target: FVector | void |
| StartShootingAll | none | void |
| StopShootingAll | none | void |
| StickySv | rot: FRotator, loc: FVector | void |
| StickyCl | TargetLoc: FVector | void |
| ExplodeStickySV | none | void |
| ExplodeStickyCl | none | void |
| DisplayJammedSticky | none | void |
| GainExtendedAmmoForAllWeps | none | void |
| InitWepSwaps | none | void |
| AiSusGunshot | none | void |
| StartPulloutWepCD | none | void |
| HideAmmoMenu | none | void |
| DisplayAmmoMenu | none | void |
| SetAmmoTypeCl | ammoType: int32 | void |
| ResetSV | none | void |
| SetAmmoTypeSV | ammoType: int32 | void |
| SpawnMolotovPart | loc: FVector | void |
| ShieldHitAll | none | void |
| FireFlashgrenadeCl | TargetLoc: FVector | void |
| FireFlashgrenadeSV | rot: FRotator | void |
| FireRopeGrenadeSV | rot: FRotator, loc: FVector | void |
| FireRopeGrenadeCl | TargetLoc: FVector | void |
| StartRepEquippedSkins | none | void |
| FireSyringeCl | TargetLoc: FVector | void |
| FireSyringeSV | rot: FRotator | void |
| GeigerTick | none | void |
| GeigerSound | none | void |
| FireChronoCl | TargetLoc: FVector | void |
| FireChronoSV | rot: FRotator, loc: FVector | void |
| StartMeleeAttackCl | none | void |
| MeleeAttackSV | none | void |
| MeleeAttackALL | none | void |
| PlayImpactSoundAll | loc: FVector, Sound: USoundBase* | void |
| MeleeHitSv | hitAct: AActor*, loc: FVector | void |
| MeleeHitCheck | none | void |
| CancelMeleeHit | none | void |
| OnAdsMeleeUpdate | none | void |
| UpdateAdsMeleeSV | adsMelee: bool | void |
| DestroyWallSV | destrWall: AActor* | void |
| PlayWallImpactSound | loc: FVector | void |
| PlayGlassBreakSoundSV | loc: FVector | void |
| UpdateEquippedWeaponsSV | EquippedWeapons: TArray | void |
| AttachFxAll | worldLoc: FVector, fx: UParticleSystem* | void |
| SetCrosshairHint | text: FText, secs: float | void |
| RemoveAdsMelee | none | void |
| ForceStopSprintCL | none | void |
| MeleeBlockHeat | none | void |
| SyringeHitSV | hitChar: AActor*, LocWorld: FVector, Rotation: FRotator | void |
| SetSyringeDecal | loc: FVector, Rotation: FRotator | void |
| FireSyringeAll | rot: FRotator | void |
| BufferShootInput | none | void |
| FireShirtCannonCL | TargetLoc: FVector | void |
| FireShirtCannonSV | rot: FRotator, loc: FVector | void |
| SwarmRemoteTick | none | void |
| SwarmRemoteClicked | none | void |

---

## ActionComponent (Component)

### Variables
| Name | Type |
|------|------|
| PlayerChar | Object |
| DeadBodyMesh | Object (Replicated) |
| DeadBodyMat | Object (Replicated) |
| inCCTV? | Bool |
| CCTVs | Array |
| currentCamID | Int |
| CurrentCCTV | Object |
| placingCam? | Bool |
| CurrentPlacementClass | Object |
| CurrentPlacAct | Object |
| SpyWidget | Object |
| SpyClothesMeshes | Array |
| SpyClothesMats | Array |
| inThermal? | Bool |
| placementRotateRoll? | Bool |
| inNinjaBox? | Bool (Replicated) |
| moneyAmount | Int (Replicated) |
| hasBombBag? | Bool (Replicated) |
| placingDrill? | Bool |
| DrillTarget | Object |
| placedC4 | Object (Replicated) |
| AbilityCdTimer | FTimerHandle |
| LookingAtPlayer | Object |
| LookingAtPlayerTimer | FTimerHandle |
| DeadBodyDeathInfoSV | FDeathInfo__pf1458230002 |
| Drone | Object (Replicated) |
| CCTV_HUD | Object |
| placedCount? | Int (Replicated) |
| PlacementLimitClasses | Array |
| PrevSlot | uint8 |
| throwingGrenade? | Bool (Replicated) |
| DeadBodyPlayerChar | Object (Replicated) |
| healing? | Bool (Replicated) |
| recentlyHeartMonitored? | Bool (Replicated) |
| passiveUses | Int (Replicated) |
| RobberClothWidget | Object |
| scoutSpeed? | Bool (Replicated) |
| buggy | Object (Replicated) |
| PlacedTeargas | Object (Replicated) |
| TwinBodyDouble | Object (Replicated) |
| oldTwinLoc | FTransform |
| destroyedEnemyVehiclesSV | Int |
| placingVault? | Bool |
| horse | Object (Replicated) |
| placedBarriers | Int |
| OldLoc | FVector |
| ninjaBoxDist | Float |
| poisoned? | Bool (Replicated) |
| heartbeatMonitorTime | FDateTime (Replicated) |
| bonusPlacements | Int (Replicated) |
| moneyBagShouldBeActive? | Bool |
| abilityExtraUses | Int |
| reinforceableSMs | Array |
| SM_InteractTime | Float |
| recentSusAction | Bool |
| deadBodyBot | Object (Replicated) |
| whistle? | Bool (Replicated) |
| cantAbility? | Bool |
| VisionDartShooter | Object |
| VisionDartTimer | FTimerHandle |
| ArmsDealerWidget | Object |
| lastCCTV | Object |
| usingRiotShield? | Bool (Replicated) |
| ebox | Object |
| lastcctvworking | Bool |
| cctvalert | Bool |
| hasDrillBag? | Bool (Replicated) |
| fishyThisRound? | Bool (Replicated) |
| bonusThisRound? | Bool |
| abilityStolen? | Bool (Replicated) |
| passiveScoreThisRound | Int (Replicated) |
| secondAbilityReady? | Bool (Replicated) |
| currentAbilityCount | Int |
| confused? | Bool (Replicated) |
| players | Array |
| PilotDrone | Object (Replicated) |
| abilityUpgrades | Int (Replicated) |
| recentlyIce | Bool |
| tiny? | Bool (Replicated) |
| hasReviveKit? | Bool (Replicated) |
| RechargeTimer | FTimerHandle |
| cameraWarned? | Bool |
| recentlySpotted? | Bool |
| spottedThisRound? | Bool (Replicated) |
| passiveRecharge | Float (Replicated) |
| tpBeforeAbility? | Bool |
| ragdolling? | TEnumAsByte<RagdollStatus> |
| RagdollStateSV | Bool (Replicated) |
| MLM_Count | Int (Replicated) |
| experimentalSerum? | Bool (Replicated) |
| bleeding | Int (Replicated) |
| bagThrowTarget | Object |
| dog | Object (Replicated) |
| revivesThisRound | Int |
| lastIceOwner | Object |
| dogKillsThisRound | Int |
| recentlyStickyJumped | Bool |
| BuildOptionsMenu | Object |
| CurrentPieMenu | Object |
| abilityKey | FKey |
| radiation | Float (Replicated) |
| hasCrown | Bool |
| royalProtected? | Bool (Replicated) |
| KarlHealTimer | FTimerHandle |
| stealMulti | Float (Replicated) |
| hasRumBag? | Bool (Replicated) |
| abilityReadySV | Bool (Replicated) |
| interactedWithPlayers | Array (Replicated) |
| swarmDrones | Array (Replicated) |
| selectedSwarmDrone | Object |
| deadBodyReported? | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| reverseForLoop | currentIndex: int32, reverse: bool, indexMax: int32, CallFunc_Multiply_IntInt_ReturnValue: int32, CallFunc_Add_IntInt_ReturnValue: int32 | int32 |
| getCurrentMlmReward | CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue_1: bool, CallFunc_SelectInt_ReturnValue: int32, CallFunc_SelectInt_ReturnValue_1: int32 | int32 |
| canCarryBodies? | none | bool |
| InitComponents | none | void |
| DropKeyReleased | tinyForce?: bool | void |
| DropDeadBodySV | none | void |
| CameraKeyPressed | none | void |
| LeftMousePressed | none | void |
| RightMousePressed | none | void |
| ChangeCam | incr?: bool | void |
| CheckCctvStillValid | destroyedCCTV: ACCTV_C* | void |
| TellSvUsingCam | usingThisCCTV: ACCTV_C* | void |
| ForceOutCCTV | none | void |
| AbilityKeyPressed | key: FKey | void |
| ToggleCamPlacement | none | void |
| PlacementTick | none | void |
| Placement_LeftClicked | none | void |
| PlaceOnSV | Class: UClass*, Trans: FTransform | void |
| ToggleSpyMenu | none | void |
| AbilityKeyReleased | none | void |
| HideSpyMenu | none | void |
| NewClothesCl | NewID: int32 | void |
| NewClothesSV | NewID: int32 | void |
| ToggleThermalVis | none | void |
| ToggleMotionDetectorPlacement | none | void |
| RotateKeyClicked | none | void |
| EquippedWeapon | none | void |
| StartPlacements | none | void |
| ToggleNinjaBox | none | void |
| UnequipWep | none | void |
| NinjaBoxSV | active?: bool | void |
| SpyBoxTick | none | void |
| DropMoneyBagSV | throwVel: FVector | void |
| ToggleBarrierPlacement | none | void |
| DropBombBagSV | throwVel: FVector | void |
| ThrowRescueSignal | none | void |
| ThrowRescueSignalSV | none | void |
| ToggleDrillPlacement | none | void |
| DrillPlacementTick | none | void |
| PlaceDrillSV | Target: AActor* | void |
| ToggleRemoteC4 | none | void |
| ExplodeC4 | none | void |
| ToggleSupplyDropPlacement | none | void |
| ResetCl | none | void |
| ForceOutThermalVision | none | void |
| ResetSV | none | void |
| ForceOutNinjaBox | none | void |
| StartAbilityCD | Time: float | void |
| AbilityCdFinished | none | void |
| StopDrillPlacement | none | void |
| LookingAtPlayerTick | none | void |
| DisplayDisguisedWidget | none | void |
| HandleDisguiseTrace | Object: UObject* | void |
| ActivateFootprintSonar | none | void |
| StartDroneFlying | none | void |
| StartDroneSV | none | void |
| AddDroneCD | none | void |
| ToggleScreenPlacement | none | void |
| RightMouseUnpressed | none | void |
| ThrowGrenade | type: UClass* | void |
| SpawnGrenadeSV | grenadeClass: UClass*, loc: FVector, forward: FRotator | void |
| StartThrowGrenade | none | void |
| GrenadeThrowAnimTP | none | void |
| StartHealing | none | void |
| SetHealingSV | none | void |
| HealTick | none | void |
| ToggleVestBagPlacement | none | void |
| StartPassiveHpReg | none | void |
| HpReg | none | void |
| ToggleRobberClothesWidget | none | void |
| RemoveRobberClothWidget | none | void |
| UseControllerYawSV | use?: bool | void |
| QueuePlacementLimitCheck | none | void |
| ChangedClassSV | none | void |
| CameraChangeKey | incr?: bool | void |
| DropDeadBodyCl | force?: bool | void |
| DropMoneyBagCl | force: bool, power: float | void |
| DropBombBagCl | force: bool, power: float | void |
| StartScoutSpeedCl | forced?: bool, secs: float, SprintSpeed: float | void |
| StartScoutSpeedSV | secs: float | void |
| StartBuggyDrive | none | void |
| AddBuggyCD | none | void |
| StartBuggySV | none | void |
| StartMadBombPlacement | none | void |
| StartDoxxingCl | none | void |
| DoxxingSV | none | void |
| GotDoxxed | none | void |
| ToggleTeargasPlacement | none | void |
| ExplodeTeargasSV | none | void |
| ToggleTwin | none | void |
| TwinTick | none | void |
| ToggleTwinSV | none | void |
| RoundStartSV | none | void |
| StartHornetDroneFlying | none | void |
| StartHornetDroneSV | none | void |
| StartRouterPlacement | none | void |
| C4ExplodedCl | none | void |
| ToggleVaultPlacement | none | void |
| VaultPlacementTick | none | void |
| StopVaultPlacement | none | void |
| ToggleTommySupplyPlacement | none | void |
| CallHorse | none | void |
| CallHorseSV | none | void |
| PostCharSelecCL | none | void |
| StartFireLadderPlacement | none | void |
| PlaceWallSV | inside?: bool, wall: ADestrWall_C* | void |
| ToggleAmmoBoxPlacement | none | void |
| ReviveNearbyCL | none | void |
| GotPoisonedSV | none | void |
| StopPoisonedSV | none | void |
| PoisonDmg | none | void |
| ToggleRemoteTurretPlacement | none | void |
| SetAbilityCdCl | Time: float | void |
| ToggleBarrellPlacement | none | void |
| UpdateClassCl | none | void |
| InteractTickExtensionsLeSm | smact: ASM_ActFast_C* | void |
| InteractExtensionSmStatic | sm: AStaticMeshActor* | void |
| InteractFinishedExtensionSmSV | sm: AStaticMeshActor*, hitLoc: FVector | void |
| SetFishyAction | none | void |
| RefreshNinjaBox | none | void |
| LoadMoneyInHeliSV | heli: AActor* | void |
| StartEMP | none | void |
| StartEmpSV | none | void |
| StartEmpAll | none | void |
| StartCantCheck | none | void |
| CantTick | none | void |
| ToggleFakeMoneyPlacement | none | void |
| CancelAbiltyCdCl | none | void |
| GotVisionDarted | shooter: APlayerChar_C* | void |
| VisionDartPinged | none | void |
| StartMaskTick | none | void |
| MaskTick | none | void |
| InteractTickSmStatic | sm: AStaticMeshActor* | void |
| InteractFinishedSmLE | sm_trans: FTransform, worldLoc: FVector | void |
| InteractExtensionSmLe | sm: ASM_ActFast_C* | void |
| ToggleArmsDealerMenu | none | void |
| RemoveArmsDealerMenu | none | void |
| WeaponPurchaseCl | purchaseID: int32 | void |
| SpawnArmsDealerDropSV | purchaseid: int32 | void |
| StartCctvRT | none | void |
| CctvRtTick | none | void |
| ToggleShield | none | void |
| EquipShieldSV | equip: bool | void |
| RemoveShield | none | void |
| AlertVigil | cctv: ACCTV_C* | void |
| DropDrillSV | none | void |
| DropDrillCl | force: bool | void |
| SetDrillPlacement | placingDrill?: bool | void |
| SetRandomClothesSV | none | void |
| FishyTick | none | void |
| ToggleWirePlacement | none | void |
| AbilityFishyCl | none | void |
| AbilityFishySV | none | void |
| FishyActionSV | none | void |
| GiveExtraPlacementCl | none | void |
| MoneyPrinterPlacement | none | void |
| UnequippedWeapon | none | void |
| ReviveTeamSV | none | void |
| StartChairmanReviveTick | none | void |
| ChairmanReviveTick | none | void |
| CopGadgetRadar | none | void |
| CallBackup | none | void |
| CallBackupSV | none | void |
| CallBackupAll | none | void |
| ToggleJokerPoison | none | void |
| SetJokerPoisonSV | none | void |
| StartConfused | none | void |
| JokerAll | none | void |
| actdelay | act: AActor* | void |
| gadgetin | Outact: AActor*, Delay: float | void |
| AbilityMaskCdTick | none | void |
| ShieldBubblePlacement | none | void |
| StartAmmoRegen | none | void |
| AmmoRegenTick | none | void |
| StartPilotDroneSV | none | void |
| StartPlaneFlying | none | void |
| VIP_Intel | none | void |
| VipIntelSV | none | void |
| ThrowMedSignal | none | void |
| ThrowMedSignalSV | none | void |
| RecentlyOnIce | iceOwner: APlayerChar_C* | void |
| ToggleShrinkCl | none | void |
| StartShrink | none | void |
| ShrinkTick | none | void |
| SetCharNewScale | A: float | void |
| StartGrow | none | void |
| GrowTick | none | void |
| ForceShrinkSV | shrink: bool | void |
| ResetShrinkSV | none | void |
| SetShrinkSV | tiny?: bool | void |
| HandleNewShrink | none | void |
| TellClToStartScoutSpeed | secs: float, SprintSpeed: float | void |
| ToggleWaterPlacement | none | void |
| SetCharNewScaleAll | A: float | void |
| DropClothesBagSV | throwVel: FVector | void |
| DropClothesBagCl | force: bool, Power: float | void |
| ToggleTrampolinePlacement | none | void |
| CheckAbilityRecharge | none | void |
| RechargeDone | none | void |
| CancelRecharge | none | void |
| StartSpyDroneSV | none | void |
| WarnCamera | none | void |
| NotifyCctvWarn | cctv: ACCTV_C* | void |
| RecentlySpotted | none | void |
| ActorAbilityPressed | forceOff: bool | void |
| RagdollTick | none | void |
| RagdollSV | ragdoll: bool | void |
| StopRagdollALL | none | void |
| ActivateExperimentalSerumCl | none | void |
| ActivateExperimentalSerumSV | none | void |
| DropKeyPress | none | void |
| CallDog | none | void |
| CallDogSV | newFollowOwner: bool | void |
| SetRecentStickyJump | none | void |
| ToggleBuildOptionsMenu | none | void |
| RemoveBuildOptionsMenu | none | void |
| ChairmanAbilityPressed | none | void |
| PieMenuAbilityKeyReleased | none | void |
| StartPieMenu | radialOptions: TArray | void |
| StartPlacementGeneric | newPlacementClass: UClass* | void |
| SlowDownTimeSV | CustomTimeDilation: float | void |
| SlowDownTimeALL | CustomTimeDilation: float | void |
| StartRoyalProtectNearby | none | void |
| StartRoyalProtect | none | void |
| StartRoyalProtectNearbySV | none | void |
| StartKarlMarxAbility | none | void |
| KarlHealTick | none | void |
| SetStealMulti | newMulti: float, duration: float | void |
| DropRumBagSV | throwVel: FVector | void |
| DropRumBagCl | force: bool, Power: float | void |
| NotifyAbilityReadySV | abilityReadySV: bool | void |
| RemoveAllScentsOfThisPlayer | none | void |
| StartRechargeTimer | Time: float | void |
| DropMoneyBagSvLimited | throwVel: FVector, onlyDropThis: int32 | void |
| StartElectricField | none | void |
| StartElectricFieldSV | none | void |
| StartElectricFieldALL | none | void |
| ToggleCanvasPlacement | none | void |
| IncrementReviveAchievment | none | void |
| UpdateOfficerBarrierCollisions | none | void |
| ReviveNearbySV_Selected | spawners: TArray | void |
| PressedSwarmAbility | none | void |
| StartSwarmDroneFlyingSV | drone: ASwarmDrone_Base_C* | void |
| SpawnSwarmDrones | none | void |
| SwitchSwarmDroneCl | increment: bool, possessNewDrone: bool | void |
| ForceSwarmDroneMoveTo | drone: ASwarmDrone_Base_C*, loc: FVector | void |
| GymBuddyWallSprintTick | none | void |
| StartSwarmPlacement | none | void |
| AdsClicked | none | void |
| ReduceCooldownByX_Client | reductionSecs: float, minRemaining: float | void |
| CustomClassAbilityKeyPressed | none | void |

---


## DestrWindowBig
**Inheritance:** `DestrWindowBig → Actor`

### Variables
| Name | Type |
|------|------|
| MIddle | Object |
| Destructible | Object |
| Box | Object |
| DefaultSceneRoot | Object |
| destroyed | Bool (Replicated) |
| DamageRadius | Float |
| ImpulseStrength | Float |
| BaseDmg | Float |
| cut | Bool (Replicated) |
| CutName | String |
| disableVisEarly? | Bool |
| breakSound | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractSV | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| CanBePenetrated? | inputDmg: float, CallFunc_Greater_FloatFloat_ReturnValue: bool | float |
| bulletsCanDmg? | helper: bool | bool |
| DestroyWall | Target: AActor*, sound: bool | void |
| ResetMesh | none | void |
| OnWindowDestroyed | none | void |

---

## AI_Base
**Inheritance:** `AI_Base → AI_Char → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| SK_SkelTemp | Object |
| vest | Object |
| HeadHitbox | Object |
| Niagara | Object |
| StaticMesh2 | Object |
| rope | Object |
| FootprintComponent | Object |
| ClothingID | uint8 (Replicated) |
| ClothingID_StartIncl | Int |
| ClothingID_EndIncl | Int |
| RotationSpeed | Float |
| TargetZ | Float |
| NextMoveToLoc | FVector |
| MoveToPreRotationTimer | FTimerHandle |
| NewRotationSpeed | Float |
| YawChangeAvg | Float |
| OldYaw | Float |
| DeathInfo | FDeathInfo__pf1458230002 |
| heartRatePlayer | Object (Replicated) |
| roped? | Bool (Replicated) |
| RotRateZ | Float (Replicated) |
| tasered? | Bool (Replicated) |
| InterestMov | Object |
| targetOverride? | Bool |
| dontRandomClothes? | Bool |
| HP | Float (Replicated) |
| dontFire | Bool |
| ropeable? | Bool |
| vested? | Bool (Replicated) |
| vestHP | Float |
| vestOwner | Object |
| useAvoid? | Bool (Replicated) |
| PathPoints | Array |
| currentGoal | FVector |
| currentGoalIndex | Int |
| humanmove? | Bool |
| humanmovetimer | FTimerHandle |
| soldOut? | Bool (Replicated) |
| dontSpawnRagdoll | Bool |
| commune? | Bool (Replicated) |
| rumReward | Int |
| hasRum? | Bool (Replicated) |
| recentlyAvoidedGadget | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| Taser | secs: float | bool |
| ignoreDistanceChecks | none | bool |
| ToggleThermal | on?: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| bulletsCanDmg? | helper: bool | bool |
| SetClothingID | NewLocalVar_0: bool, CallFunc_RandomIntegerInRange_ReturnValue: int32, CallFunc_Conv_IntToByte_ReturnValue: uint8 | void |
| UserConstructionScript | CallFunc_K2_AttachToComponent_ReturnValue: bool, CallFunc_K2_AttachToComponent_ReturnValue_1: bool | void |
| StartRandomMovement | none | void |
| StartNewTask | none | void |
| StartRotateCharacter | none | void |
| RotateTick | none | void |
| StartMoveAfterRot | none | void |
| UpdateRotSpeed | none | void |
| CheckTurnAnim | none | void |
| StartCheckTurnAnim | none | void |
| DestroyHandle | none | void |
| SetTurnSpeed | none | void |
| Tasered | Duration: float | void |
| CheckMovStatus | none | void |
| TargetOverride | none | void |
| AiStartMoveTo | PathEnd: FVector | void |
| AiMoveTick | none | void |
| HumanMoveTimeout | none | void |
| SlowDownTimeSV | none | void |
| SlowDownTimeALL | none | void |

---

## SafeDoor
**Inheritance:** `SafeDoor → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| AiLocation | Object |
| Box | Object |
| ParticleSystem | Object |
| Widget | Object |
| Sphere | Object |
| CombinedBriefcase1 | Object |
| CombinedBriefcase | Object |
| Bomb | Object |
| StaticMesh2 | Object |
| StaticMesh1 | Object |
| VaultDoor | Object |
| BeepSound | Object |
| BeepDelay | Float |
| bombPlanted? | Bool (Replicated) |
| opened? | Bool (Replicated) |
| smoke? | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| getPaintingValue | easel: ACanvasEasel_C* | FVector |
| GetAiInteractTraceLocation | none | FVector |
| PlayerAiCanInteract | none | bool |
| PlayerAiInteract | playerai: APlayerAI_C*, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool | bool |
| PlayerAiInteractTimer | playerai: APlayerAI_C* | float |
| GetAiInteractWorldLoc | CallFunc_K2_GetComponentLocation_ReturnValue: FVector | FVector |
| CopInter? | none | bool |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| destroyedCl | CallFunc_GetTransform_ReturnValue: FTransform, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_FinishSpawningActor_ReturnValue: ASafeDoorDestructible_C* | void |
| StartCountdown | none | void |
| Explode | none | void |
| StartBeep | none | void |
| BeepLoop | none | void |
| SetBombVis | none | void |
| TickVis | none | void |
| DmgHook | none | void |

---

## DestrWall
**Inheritance:** `DestrWall → Actor`

### Variables
| Name | Type |
|------|------|
| OverlapBox | Object |
| DmgCheckPoint | Object |
| StaticMesh1 | Object |
| StaticMesh | Object |
| Scene1ins | Object |
| SceneOuts | Object |
| AI_Box | Object |
| NavModifier | Object |
| RocketTarget1 | Object |
| RocketTarget | Object |
| Box | Object |
| DestructibleInt | Object |
| Destructible | Object |
| DefaultSceneRoot | Object |
| destroyed | Bool (Replicated) |
| armorInside? | Bool (Replicated) |
| armorOutside? | Bool (Replicated) |
| armorOutsideHp | Float |
| armorInsideHp | Float |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| CanBePenetrated? | inputDmg: float, CallFunc_SelectFloat_ReturnValue: float | float |
| bulletsCanDmg? | helper: bool | bool |
| DestroyWall | Target: AActor* | void |
| CheckTargetVis | none | void |
| PlacementTick | inside?: bool | void |
| Undestroy | none | void |
| ResetDestr | none | void |
| BreakSoundALL | none | void |

---

## CCTV
**Inheritance:** `CCTV → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| WidgetRed | Object |
| Widget | Object |
| SceneCaptureComponent2D | Object |
| Niagara | Object |
| StaticMesh2 | Object |
| MineScene | Object |
| ParticleSystem | Object |
| PointLight | Object |
| ChamelonPP | Object |
| Camera | Object |
| Dot | Object |
| StaticMesh | Object |
| StaticMesh1 | Object |
| used? | Bool (Replicated) |
| broken? | Bool (Replicated) |
| neverFlash? | Bool |
| brokenTemp? | Bool (Replicated) |
| mined? | Bool (Replicated) |
| emp? | Bool (Replicated) |
| RoofBox | Object |
| players | Array |
| warned? | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| EmpStart | duration: float | bool |
| ignoreDistanceChecks | none | bool |
| destroyedCl | CallFunc_GetPlayerCharacter_ReturnValue: ACharacter*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool | void |
| UserConstructionScript | none | void |
| CheckusedSV | none | void |
| CheckDotVis | none | void |
| StartBrokenTempSV | none | void |
| RemoveExplosionSoundAll | none | void |
| EmpBegin | Duration: float | void |
| UpdateMaskHide | none | void |
| GetPlayers | none | void |
| SmartTick | none | void |
| TickVis | none | void |
| WarnLocal | none | void |

---

## SupplyDrop
**Inheritance:** `SupplyDrop → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| ChildActor | Object |
| ChildActor1 | Object |
| Widget | Object |
| BonusMesh | Object |
| BaseMesh | Object |
| uses? | Int (Replicated) |
| w1 | Object |
| w2 | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C* | FText |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| RefreshUses | none | void |
| TickVis | none | void |

---

## RiotBarrier
**Inheritance:** `RiotBarrier → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Box | Object |
| StaticMesh1 | Object |
| StaticMesh | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool | FText |

---

## MotionDetector
**Inheritance:** `MotionDetector → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Niagara | Object |
| StaticMesh2 | Object |
| Capsule | Object |
| StaticMesh1 | Object |
| StaticMesh | Object |
| emp? | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool | FText |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| EmpStart | duration: float | bool |
| RefreshLaserLength | none | void |
| destroyedCl | none | void |
| EmpBegin | Duration: float | void |

---

## RemoteC4
**Inheritance:** `RemoteC4 → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| FrontScene | Object |
| BackScene | Object |
| PartDmgSphere | Object |
| FullDmgSphere | Object |
| StaticMesh | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| GetInteractName | PlayerChar: APlayerChar_C* | FText |
| DontExplodeAll | none | void |

---

## Rocket
**Inheritance:** `Rocket → Actor`

### Variables
| Name | Type |
|------|------|
| ParticleSystem | Object |
| Sphere | Object |
| RocketMesh | Object |
| ProjectileMovement | Object |
| DefaultSceneRoot | Object |
| OldLoc | FVector |
| noDmg? | Bool |
| doCollisionChecks? | Bool |
| dead? | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## HeavyGrenade
**Inheritance:** `HeavyGrenade → Actor`

### Variables
| Name | Type |
|------|------|
| Damage | Object |
| Capsule | Object |
| StaticMesh | Object |
| ProjectileMovement | Object |
| client? | Bool |
| LastVel | FVector |
| hitAct | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## SmokeGrenade
**Inheritance:** `SmokeGrenade → Actor`

### Variables
| Name | Type |
|------|------|
| Capsule | Object |
| StaticMesh | Object |
| ProjectileMovement | Object |
| client? | Bool |
| smoke?notTeargas | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## TeargasAct
**Inheritance:** `TeargasAct → Actor`

### Variables
| Name | Type |
|------|------|
| Sphere | Object |
| StaticMesh | Object |
| ParticleSystem | Object |
| DefaultSceneRoot | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| VisColl | l1: FVector, l2: FVector, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_LineIntersectsSphere_blocked_: bool | bool |
| DamageTick | none | void |

---

## DrillableFloor
**Inheritance:** `DrillableFloor → Actor`

### Variables
| Name | Type |
|------|------|
| Widget | Object |
| ChildActor | Object |
| LadderScene | Object |
| DrillAct | Object |
| PreviewDrill | Object |
| CombinedFloorHoleFill | Object |
| StaticMesh | Object |
| DefaultSceneRoot | Object |
| drillPlaced? | Bool (Replicated) |
| drillloc | FVector |
| Corner1 | FVector |
| Corner2 | FVector |
| Corner3 | FVector |
| Corner4 | FVector |
| CurrentCorner | Int (Replicated) |
| targetLoc | FVector |
| finished? | Bool (Replicated) |
| ladder | Object |
| spawnLadder | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ToggleDrillPreview | active?: bool | bool |
| UserConstructionScript | none | void |
| TickVis | none | void |

---

## DrillForFloor
**Inheritance:** `DrillForFloor → Actor`

### Variables
| Name | Type |
|------|------|
| Botgroundcheck | Object |
| botfloorcheck | Object |
| MainBotLoc | Object |
| ParticleSystem | Object |
| Audio | Object |
| StaticMesh | Object |
| DefaultSceneRoot | Object |
| running? | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| getPaintingValue | easel: ACanvasEasel_C*, CallFunc_Not_PreBool_ReturnValue: bool | FVector |
| GetAiInteractTraceLocation | none | FVector |
| PlayerAiCanInteract | none | bool |
| CopInter? | none | bool |
| PlayerAiInteract | playerai: APlayerAI_C* | bool |
| PlayerAiInteractTimer | playerai: APlayerAI_C* | float |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |

---

## Ragdoll
**Inheritance:** `Ragdoll → Actor`

### Variables
| Name | Type |
|------|------|
| SK_SkelTemp | Object |
| Widget | Object |
| SkeletalMesh | Object |
| DefaultSceneRoot | Object |
| Mesh | Object (Replicated) |
| MeshMaterial | Object (Replicated) |
| PoseSnap | FPoseSnapshot |
| Spawner | Object |
| deathInfo | FDeathInfo__pf1458230002 |
| oldbones | Array |
| lastCarrierWasPlayer? | Bool |
| lastCarrierRobber? | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| getPaintingValue | easel: ACanvasEasel_C*, CallFunc_NotEqual_ObjectObject_ReturnValue: bool | FVector |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool | bool |
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| RefreshPhysics | none | bool |
| InteractClAlt | PlayerChar: APlayerChar_C* | bool |
| ClTimer | char: APlayerChar_C*, CallFunc_isClass__is_: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | float |
| InteractCl | PlayerChar: APlayerChar_C* | bool |
| fired? | CallFunc_EqualEqual_ByteByte_ReturnValue: bool | bool |
| InteractAltSV | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue: bool | bool |
| UpdateMeshMat | none | void |
| UserConstructionScript | none | void |
| TickVis | none | void |
| RefreshPhys | none | void |
| PrintBones | none | void |

---

## RagdollSpawn
**Inheritance:** `RagdollSpawn → Actor`

### Variables
| Name | Type |
|------|------|
| DefaultSceneRoot | Object |
| Mesh | Object (Replicated) |
| MeshMaterial | Object (Replicated) |
| PoseSnap | FPoseSnapshot |
| MeshRep? | Bool |
| MatRep? | Bool |
| Ragdoll | Object |
| deathInfo | FDeathInfo__pf1458230002 (Replicated) |
| deadplayerchar | Object (Replicated) |
| lastCarrier | Object (Replicated) |
| officerReported? | Bool (Replicated) |
| deadBot | Object (Replicated) |
| backupReported? | Bool (Replicated) |
| radiation | Float (Replicated) |
| scentRemoved? | Bool |
| recentlyAiInteracted | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetAiInteractTraceLocation | none | FVector |
| PlayerAiCanInteract | none | bool |
| PlayerAiInteractTimer | playerai: APlayerAI_C* | float |
| GetAiInteractWorldLoc | none | FVector |
| CopInter? | none | bool |
| TimerAlt | none | bool |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C*, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | bool |
| lastCarrierCop? | K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool | bool |
| killedByCop? | K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool | bool |
| SpawnRagdoll | none | void |
| SelfDestroy | none | void |
| OnPlayerSwappedClothes | playerchar: APlayerChar_C* | void |
| SpawnRagdollMulti | Mesh: USkeletalMesh*, MeshMaterial: UMaterialInterface* | void |

---

## BombBag
**Inheritance:** `BombBag → Actor`

### Variables
| Name | Type |
|------|------|
| StaticMesh | Object |
| Widget | Object |
| bags | Array |
| dontdraw | Bool |
| throwForce | FVector |
| lastToucher | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetAiInteractTraceLocation | none | FVector |
| PlayerAiCanInteract | none | bool |
| PlayerAiInteract | playerai: APlayerAI_C*, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_HasAuthority_ReturnValue: bool | bool |
| PlayerAiInteractTimer | playerai: APlayerAI_C* | float |
| GetAiInteractWorldLoc | none | FVector |
| CopInter? | none | bool |
| GetItemName | none | FString |
| RefreshPhysics | none | bool |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| GetCustomTrace | none | FHitResult |
| GetCustomPingSettings | Executor: APawn* | TArray |
| RefreshPhys | none | void |
| TickVis | none | void |
| getBags | none | void |

---

## MoneyBag
**Inheritance:** `MoneyBag → Actor`

### Variables
| Name | Type |
|------|------|
| Sphere | Object |
| StaticMesh | Object |
| Widget1 | Object |
| Widget | Object |
| moneyValue | Int (Replicated) |
| spotted | Bool |
| paintbag? | Bool (Replicated) |
| explode | Bool |
| droppedByCop? | Bool (Replicated) |
| autoCombine? | Bool |
| throwForce | FVector |
| lastToucher | Object |
| radiation | Float (Replicated) |
| throwStartLoc | FVector |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetRadiation | loc: FVector | float |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool | bool |
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| GetAiInteractTraceLocation | none | FVector |
| PlayerAiCanInteract | none | bool |
| PlayerAiInteractTimer | playerai: APlayerAI_C* | float |
| GetAiInteractWorldLoc | none | FVector |
| CopInter? | none | bool |
| GetItemName | none | FString |
| RefreshPhysics | none | bool |
| ignoreDistanceChecks | none | bool |
| RefreshPhys | none | void |
| TickVis | none | void |
| ExplodeAll | none | void |

---

## RescueSignal
**Inheritance:** `RescueSignal → Actor`

### Variables
| Name | Type |
|------|------|
| SmokeExit | Object |
| ParticleSystem | Object |
| StaticMesh | Object |
| DefaultSceneRoot | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| SendHeli | none | void |

---

## RescueHeliFlying
**Inheritance:** `RescueHeliFlying → Actor`

### Variables
| Name | Type |
|------|------|
| BagZone | Object |
| Audio | Object |
| Cylinder | Object |
| Box3 | Object |
| PilotMesh | Object |
| Box2 | Object |
| Box1 | Object |
| Box | Object |
| SkeletalMesh | Object |
| targetLoc | FVector |
| hasTarget? | Bool |
| moveToLoc | FVector (Replicated) |
| lastTrySucc? | Bool |
| moving? | Bool (Replicated) |
| rotating? | Bool |
| rotatedThisLanding? | Bool |
| recentlyMoved | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| StartRotating | none | void |
| PostMoving | none | void |
| SetRecentlyMoved | none | void |

---

## MoneyBaseAct
**Inheritance:** `MoneyBaseAct → Actor`

### Variables
| Name | Type |
|------|------|
| SplineMesh | Object |
| StaticMesh | Object |
| DefaultSceneRoot | Object |
| moneyValue | Int (Replicated) |
| pickupTimer | Float |
| pickupName | FText |
| attachedTo | Object (Replicated) |
| isSecretFile? | Bool |
| isJewelry? | Bool |
| classLimited | uint8 |
| radiation | Float (Replicated) |
| showMoneyValue? | Bool |
| defaultMat | Object |
| cloakedDopey | Object (Replicated) |
| prevCloaked | Bool |
| readBySwarm? | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetRadiation | loc: FVector | float |
| GetAiInteractTraceLocation | none | FVector |
| PlayerAiCanInteract | CallFunc_IsValid_ReturnValue: bool | bool |
| PlayerAiInteractTimer | playerai: APlayerAI_C* | float |
| GetAiInteractWorldLoc | none | FVector |
| CopInter? | none | bool |
| GetItemName | CallFunc_Conv_TextToString_ReturnValue: FString | FString |
| ignoreDistanceChecks | none | bool |
| PlayerInteracted | player: APlayerChar_C* | void |
| SaveMeshMat | none | void |
| CloakTick | none | void |

---

## SafeDoorDestructible
**Inheritance:** `SafeDoorDestructible → Actor`

### Variables
| Name | Type |
|------|------|
| Destructible | Object |
| DefaultSceneRoot | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| RestartCl | none | bool |
| RestartSV | none | bool |

---

## TechDrone
**Inheritance:** `TechDrone → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| GymBag | Object |
| Widget | Object |
| DrillBag | Object |
| weaponcrate | Object |
| Niagara | Object |
| StaticMesh2 | Object |
| MineScene | Object |
| Camera | Object |
| SpringArm | Object |
| BombBag | Object |
| MoneyFX | Object |
| MoneyBag | Object |
| motorsound | Object |
| HP | Float (Replicated) |
| DroneHUD | Object |
| hasMoneyBag? | Bool (Replicated) |
| moneyAmountSV | Int (Replicated) |
| lookingAtMoneyBag | Object |
| LastPossessedPlayer | Object |
| lookingAtBombBag | Object |
| hasBombBag? | Bool (Replicated) |
| lostConnection? | Bool |
| mined? | Bool (Replicated) |
| robber? | Bool |
| emp? | Bool (Replicated) |
| LookingAtWeaponCrate | Object |
| attachedwepcraterepl | Object (Replicated) |
| attachwepcrate | Object |
| hasDrillBag? | Bool (Replicated) |
| LookingAtDrill | Object |
| hasGymBag? | Bool (Replicated) |
| LookingAtGymBag | Object |
| lookingAtEmp | Object |
| lookingAtRepair | Object |
| lastControlRot | FRotator |
| recentlyPossessed | Bool |
| blockInput? | Bool |
| leftMouseText | FText |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| EmpStart | duration: float, CallFunc_DealDmg_dead: bool | bool |
| isSus | none | bool |
| ignoreDistanceChecks | none | bool |
| CanBePenetrated? | inputDmg: float | float |
| bulletsCanDmg? | helper: bool | bool |
| customDestroyedHandling | none | bool |
| TellClPossessed | none | void |
| WantsUnpossessCl | none | void |
| WantsUnpossessSV | possessOverride: APawn* | void |
| DropBagSV | none | void |
| PickupBagSV | bag: AMoneyBag_C* | void |
| TellClGotUnpos | none | void |
| PickupBombBagSV | bag: ABombBag_C* | void |
| DropBombBagSV | none | void |
| JammedSV | none | void |
| JammedCL | none | void |
| EmpBegin | Duration: float | void |
| PickupWeaponCrateSV | crate: AWeaponCrate_C* | void |
| DropWeaponCrateSV | none | void |
| DropDrillBagSV | none | void |
| PickupDrillSV | bag: ADrillBag_C* | void |
| TickVis | none | void |
| DropGymBagSV | none | void |
| PickupGymBag | bag: AReviveKit_C* | void |
| EmpSV | act: AActor* | void |
| PuddleFix | none | void |
| Unpossessed_Event | none | void |
| RepairDroneSV | act: AActor* | void |

---

## PortalImpossibleAct
**Inheritance:** `PortalImpossibleAct → BP_Portal → Actor`

### Variables
| Name | Type |
|------|------|
| PortalSlimMesh | Object |
| Plane | Object |
| StaticMesh1 | Object |
| StaticMesh | Object |
| Cube | Object |
| DestroyLoc | FVector |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| InteractTimer | playerchar: APlayerChar_C* | bool |
| ignoreDistanceChecks | none | bool |
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | FText |
| CanBePenetrated? | inputDmg: float | float |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, CallFunc_HasAuthority_ReturnValue: bool | bool |
| bulletsCanDmg? | helper: bool | bool |
| UserConstructionScript | CallFunc_Conv_BoolToFloat_ReturnValue: float, K2Node_SwitchInteger_CmpSuccess: bool | void |

---

## MolotovPart
**Inheritance:** `MolotovPart → Actor`

### Variables
| Name | Type |
|------|------|
| ParticleSystem2 | Object |
| NavModifier | Object |
| Sphere | Object |
| ParticleSystem | Object |
| DefaultSceneRoot | Object |
| dmgOFF? | Bool |
| extraclasses | Array |
| lifeTime | Float |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| Damage | none | void |
| DestroyALL | none | void |

---

## ThrowedGrenade_Molotov
**Inheritance:** `ThrowedGrenade_Molotov → ThrowedGrenade → Actor`

### Variables
| Name | Type |
|------|------|
| ParticleSystem | Object |
| HitLoc | FVector |
| hitpawn | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| SpawnMolotovPart | loc: FVector | void |

---

## ThrowedGrenade_Decoy
**Inheritance:** `ThrowedGrenade_Decoy → ThrowedGrenade → Actor`

### Variables
| Name | Type |
|------|------|
| ParticleSystem | Object |
| Damage | Object |
| client? | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| SpawnMolotovPart | loc: FVector | void |

---

## ThrowedGrenadeFlash
**Inheritance:** `ThrowedGrenadeFlash → ThrowedGrenade → Actor`

### Variables
| Name | Type |
|------|------|

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## VestBag
**Inheritance:** `VestBag → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| ChildActor1 | Object |
| ChildActor | Object |
| Widget | Object |
| SM_Prop_TrashBag_02 | Object |
| SM_Prop_TrashBag_01 | Object |
| StaticMesh | Object |
| remainingVests | Int (Replicated) |
| w1 | Object |
| w2 | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| TickVis | none | void |

---

## DestrWindowBigLE
**Inheritance:** `DestrWindowBigLE → Actor`

### Variables
| Name | Type |
|------|------|
| MIddle | Object |
| Destructible | Object |
| Box | Object |
| DefaultSceneRoot | Object |
| destroyed | Bool (Replicated) |
| DamageRadius | Float |
| ImpulseStrength | Float |
| BaseDmg | Float |
| cut | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractSV | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| CanBePenetrated? | inputDmg: float, CallFunc_Greater_FloatFloat_ReturnValue: bool | float |
| bulletsCanDmg? | helper: bool | bool |
| DestroyWall | Target: AActor*, sound?: bool | void |
| ResetMesh | none | void |

---

## DestrWindowSkylightLE
**Inheritance:** `DestrWindowSkylightLE → DestrWindowBig → Actor`

### Variables
| Name | Type |
|------|------|

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## DestrWindowSmallSingleLE
**Inheritance:** `DestrWindowSmallSingleLE → DestrWindowBig → Actor`

### Variables
| Name | Type |
|------|------|
| Box1 | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| OnWindowDestroyed | none | void |

---

## BombBuggy
**Inheritance:** `BombBuggy → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| Camera | Object |
| SpringArm | Object |
| Sphere | Object |
| e1 | Object |
| e | Object |
| StaticMesh | Object |
| motorsound | Object |
| HP | Float (Replicated) |
| BuggyHUD | Object |
| LastPossessedPlayer | Object |
| YawChangeAvg | Float |
| OldYaw | Float |
| lostConnection? | Bool |
| recycled | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | FText |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| isSus | none | bool |
| CanBePenetrated? | inputDmg: float | float |
| bulletsCanDmg? | helper: bool | bool |
| TellClPossessed | none | void |
| WantsUnpossessCl | none | void |
| WantsUnpossessSV | none | void |
| TellClGotUnpos | none | void |
| SelfDestructSV | none | void |
| CheckTurnAnim | none | void |
| StartCheckTurnAnim | none | void |
| JammedSV | none | void |
| JammedCL | none | void |
| DestroyEnableColl | none | void |

---

## MadmanBomb
**Inheritance:** `MadmanBomb → Actor`

### Variables
| Name | Type |
|------|------|
| Scene1 | Object |
| Scene | Object |
| Widget | Object |
| TextRender | Object |
| Sphere | Object |
| StaticMesh | Object |
| DefaultSceneRoot | Object |
| ExplodeTime | FDateTime (Replicated) |
| exploded | Bool |
| destroyedsafedoors | Int |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| getPaintingValue | easel: ACanvasEasel_C* | FVector |
| GetAiInteractTraceLocation | none | FVector |
| PlayerAiCanInteract | none | bool |
| CopInter? | none | bool |
| PlayerAiInteract | playerai: APlayerAI_C* | bool |
| PlayerAiInteractTimer | playerai: APlayerAI_C* | float |
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_Not_PreBool_ReturnValue: bool | FText |
| ignoreDistanceChecks | none | bool |
| InteractSV | PlayerChar: APlayerChar_C* | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| ExplodeAll | none | void |
| ExplodeSV | none | void |
| Beep | none | void |
| TickVis | none | void |

---

## TeargasTrap
**Inheritance:** `TeargasTrap → Actor`

### Variables
| Name | Type |
|------|------|
| FullDmgSphere | Object |
| Box | Object |
| SM_Wep_Grenade_01 | Object |
| ParticleSystem | Object |
| DefaultSceneRoot | Object |
| triggered? | Bool (Replicated) |
| SmokeSound | Object |
| ignoreActs | Array |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool | FText |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| VisColl | l1: FVector, l2: FVector, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_LineIntersectsSphere_blocked_: bool | bool |
| ToggleThermal | on?: bool, CallFunc_Not_PreBool_ReturnValue: bool | bool |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool | bool |
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| DamageTick | none | void |
| ActivateSV | none | void |
| DeactivateParticle | none | void |

---

## RC_Disabler
**Inheritance:** `RC_Disabler → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Niagara | Object |
| StaticMesh2 | Object |
| PointLight | Object |
| Sphere | Object |
| StaticMesh | Object |
| emp? | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| EmpStart | duration: float | bool |
| Blinking | none | void |
| EmpBegin | Duration: float | void |

---

## DestrWindowVentSound
**Inheritance:** `DestrWindowVentSound → Actor`

### Variables
| Name | Type |
|------|------|
| Destructible | Object |
| MIddle | Object |
| Box | Object |
| DefaultSceneRoot | Object |
| destroyed | Bool (Replicated) |
| DamageRadius | Float |
| ImpulseStrength | Float |
| BaseDmg | Float |
| cut | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractSV | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| CanBePenetrated? | inputDmg: float, CallFunc_Greater_FloatFloat_ReturnValue: bool | float |
| bulletsCanDmg? | helper: bool | bool |
| DestroyWall | Target: AActor*, sound: bool | void |
| ResetMesh | none | void |

---

## DestroyedVaultDoor
**Inheritance:** `DestroyedVaultDoor → Actor`

### Variables
| Name | Type |
|------|------|
| VaultDoor | Object |
| DefaultSceneRoot | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| getPaintingValue | easel: ACanvasEasel_C* | FVector |
| ToggleDrillPreview | active?: bool | bool |
| ToggleDrillPlacementGuide | active?: bool | bool |

---

## TommyDrop
**Inheritance:** `TommyDrop → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Widget | Object |
| BonusMesh3 | Object |
| BonusMesh2 | Object |
| BonusMesh1 | Object |
| BonusMesh | Object |
| BaseMesh | Object |
| uses? | Int (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetAiInteractTraceLocation | none | FVector |
| PlayerAiCanInteract | none | bool |
| PlayerAiInteractTimer | playerai: APlayerAI_C* | float |
| GetAiInteractWorldLoc | none | FVector |
| CopInter? | none | bool |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| RefreshUses | none | void |
| TickVis | none | void |

---

## HorseChar
**Inheritance:** `HorseChar → MyCharacter → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| teamnameWidget | Object |
| Capsule6 | Object |
| UnsaddlePos5 | Object |
| Capsule5 | Object |
| UnsaddlePos4 | Object |
| Capsule4 | Object |
| UnsaddlePos3 | Object |
| Capsule3 | Object |
| UnsaddlePos2 | Object |
| Capsule2 | Object |
| Camera | Object |
| SpringArm | Object |
| Capsule1 | Object |
| UnsaddlePos1 | Object |
| Capsule | Object |
| UnsaddlePos | Object |
| player | Object |
| reins | Object |
| saddle | Object |
| LastPossessedPlayer | Object |
| HP | Float |
| HorseHUD | Object |
| playerRiding | Object (Replicated) |
| oldplayer | Object |
| playerDismountHelper | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| getPaintingValue | easel: ACanvasEasel_C* | FVector |
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| UserConstructionScript | CallFunc_K2_AttachToComponent_ReturnValue: bool | void |
| TellClPossessed | none | void |
| ForceUnpossessOnCl | none | void |
| WantsUnpossessSV | none | void |
| TellHorseMoveTo | act: AActor* | void |
| TellClGotUnpossessed | none | void |
| ForceSpec | none | void |
| RegHP | none | void |
| NeighAll | none | void |
| TickTeamName | none | void |
| SlowDownTimeSV | none | void |
| SlowDownTimeALL | none | void |

---

## FireLadderAct
**Inheritance:** `FireLadderAct → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Box2 | Object |
| StaticMesh | Object |
| Box | Object |
| Box1 | Object |
| ready? | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool | FText |
| AiBlockFix | none | void |

---

## AmmoDrop
**Inheritance:** `AmmoDrop → Actor`

### Variables
| Name | Type |
|------|------|
| Widget | Object |
| BonusMesh | Object |
| BaseMesh | Object |
| DefaultSceneRoot | Object |
| uses? | Int (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C* | FText |
| ignoreDistanceChecks | none | bool |
| InteractSV | PlayerChar: APlayerChar_C*, Temp_int_Variable: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue: int32 | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| RefreshUses | none | void |
| TickVis | none | void |

---

## HorseRagdoll
**Inheritance:** `HorseRagdoll → Actor`

### Variables
| Name | Type |
|------|------|
| SkeletalMesh | Object |
| DefaultSceneRoot | Object |
| PoseSnap | FPoseSnapshot |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| RestartSV | none | bool |
| RestartCl | none | bool |

---

## DestrWallNewYork2
**Inheritance:** `DestrWallNewYork2 → Actor`

### Variables
| Name | Type |
|------|------|
| AI_Box | Object |
| NavModifier | Object |
| RocketTarget1 | Object |
| RocketTarget | Object |
| Box | Object |
| DestructibleInt | Object |
| Destructible | Object |
| DefaultSceneRoot | Object |
| destroyed | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| CanBePenetrated? | inputDmg: float | float |
| bulletsCanDmg? | helper: bool | bool |
| DestroyWall | Target: AActor* | void |
| CheckTargetVis | none | void |

---

## DestrWallNY
**Inheritance:** `DestrWallNY → DestrWall → Actor`

### Variables
| Name | Type |
|------|------|

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## ProximityMine
**Inheritance:** `ProximityMine → Actor`

### Variables
| Name | Type |
|------|------|
| Widget | Object |
| Sphere | Object |
| StaticMesh | Object |
| DefaultSceneRoot | Object |
| parentActor | Object |
| forceDmgAct | Object |
| damagedActs | Array |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, CallFunc_HasAuthority_ReturnValue: bool | bool |
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| TickVis | none | void |

---

## RemoteTurret
**Inheritance:** `RemoteTurret → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Niagara | Object |
| StaticMesh5 | Object |
| TextRender | Object |
| Muzzle | Object |
| Camera | Object |
| SK_Wep_MachineGun_01 | Object |
| PointLight | Object |
| StaticMesh3 | Object |
| StaticMesh4 | Object |
| StaticMesh | Object |
| GunScene | Object |
| CombinedSentryLegs | Object |
| Scene | Object |
| StaticMesh1 | Object |
| StaticMesh2 | Object |
| RotSV | Float |
| foundTarget? | Bool (Replicated) |
| target | Object (Replicated) |
| shooting? | Bool |
| curve | Object |
| OldTarget | Object |
| HpRepl | Float (Replicated) |
| emp? | Bool (Replicated) |
| pickedUp?_0 | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| getPaintingValue | easel: ACanvasEasel_C* | FVector |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool | FText |
| EmpStart | duration: float | bool |
| RotateTick | none | void |
| UpdateTarget | none | void |
| Shoot | none | void |
| Repair | none | void |
| EmpBegin | Duration: float | void |

---

## BoomBarrell
**Inheritance:** `BoomBarrell → Actor`

### Variables
| Name | Type |
|------|------|
| Sphere | Object |
| StaticMesh | Object |
| DefaultSceneRoot | Object |
| HitLoc | FVector |
| noExpl | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | FText |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool | bool |
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| SpawnMolotovPart | loc: FVector | void |
| ExplodeDelaySV | delay: float | void |
| NotExplodeALL | none | void |
| DestroyNoExpl | none | void |

---

## StickyGrenade
**Inheritance:** `StickyGrenade → Actor`

### Variables
| Name | Type |
|------|------|
| Damage | Object |
| Capsule | Object |
| StaticMesh | Object |
| ProjectileMovement | Object |
| client? | Bool |
| LastVel | FVector |
| closestDis | Float |
| SocketName | Name (Replicated) |
| AttachedtoAct | Object |
| dontExplode? | Bool |
| RelativeAttachLoc | FVector (Replicated) |
| replloc | Bool |
| replact | Bool |
| AttachedToComp | Object (Replicated) |
| absoluteLoc | FVector (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractSV | PlayerChar: APlayerChar_C* | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| GetInteractName | PlayerChar: APlayerChar_C* | FText |
| DontExplodeAll | none | void |
| DrawAll | Origin: FVector | void |
| ReplCheck | none | void |
| CheckOwnerValid | none | void |

---

## WallArmor
**Inheritance:** `WallArmor → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Box | Object |
| StaticMesh | Object |
| Scene1ins | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## PlayerAI
**Inheritance:** `PlayerAI → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| SK_SkelTemp | Object |
| Niagara | Object |
| StaticMesh2 | Object |
| BoxingCaps | Object |
| HeadHitbox | Object |
| DoorCapsule | Object |
| teamnameWidget | Object |
| Camera | Object |
| SpringArm | Object |
| TP_Weapon | Object |
| Tp_MuzzleFlashLight | Object |
| Tp_MuzzleEnd | Object |
| currentWeaponID | uint8 (Replicated) |
| weaponID | uint8 |
| YawChangeAvg | Float |
| OldYaw | Float |
| Pitch | Float |
| CurrentWepRow | FWeaponTypesStructs__pf3747386746 |
| equippedWeapon | uint8 |
| shootTarget | Object (Replicated) |
| currentRecoilMulti | Float |
| shooting? | Bool |
| isBoxing? | Bool |
| currentAmmoSV | Int |
| ReloadingSV? | Bool (Replicated) |
| walkingSvLoc? | Bool |
| state | TEnumAsByte<PlayerAiState> |
| investigatingPawn | Object (Replicated) |
| difficulty | Int (Replicated) |
| walkingTargetLoc | FVector |
| HP | Float |
| robber? | Bool |
| sleeping? | Bool (Replicated) |
| sprintingSV? | Bool (Replicated) |
| LastOpenedDoor | Object |
| LastHit | Object |
| InteractTarget | Object (Replicated) |
| pingCD? | Bool |
| recentlyPingedItems | Array |
| CurrentLadder | Object |
| ladderduration | Float |
| ladderdown | Bool |
| movetoloc | FVector |
| LadderTimer | FTimerHandle |
| WalkingSvToAct | Bool |
| WalkingSvInter | Bool |
| oldState | TEnumAsByte<PlayerAiState> |
| InvestigatingTargetLoc | FVector |
| dead? | Bool (Replicated) |
| flashed? | Bool (Replicated) |
| Doors | Array |
| recentlyOpenedDoors | Array |
| DeathInfo | FDeathInfo__pf1458230002 (Replicated) |
| ignoreInteractTraceClasses | Array |
| ignores | Array |
| TargetZ | Float (Replicated) |
| boxing? | Bool (Replicated) |
| boxTarget | Object (Replicated) |
| interactStartTarget | Object |
| closeInter | Bool |
| interactTries | Int |
| tasered? | Bool (Replicated) |
| dumpspot | Object |
| interacttimerhandle | FTimerHandle |
| radiation | Float (Replicated) |
| debug? | Bool |
| recentlyDamagedByDog? | Object |
| FireHelper | Object |
| forbiddenInteracts | Array |
| recentlyRespawned? | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| getPaintingValue | easel: ACanvasEasel_C*, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Greater_IntInt_ReturnValue: bool | FVector |
| GetRadiation | loc: FVector | float |
| Taser | secs: float | bool |
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| helperPrint | InString: FString | void |
| AddRecoil | RecoilAdd: float, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FClamp_ReturnValue: float | void |
| UserConstructionScript | CallFunc_K2_AttachToComponent_ReturnValue: bool, CallFunc_K2_AttachToComponent_ReturnValue_1: bool | void |
| CheckTurnAnim | none | void |
| EquipWeapon | WepID: uint8 | void |
| Shoot_TickClTP | none | void |
| Shoot_TickClStartTP | none | void |
| FireBulletClTP | Randomness: float | void |
| SpawnBulletClTP | TargetLoc: FVector | void |
| ShotTpFX | none | void |
| StartShootingSV | shootingTarget: AActor* | void |
| StopShootingSV | none | void |
| SetRot | none | void |
| InitWepSV | wepID: uint8 | void |
| ReloadAnimTP | none | void |
| StartReloading | none | void |
| ReloadSuccessfull | none | void |
| ReloadCancelled | none | void |
| MoveToTargetLoc | Destination: FVector | void |
| DoStuffSV | none | void |
| SetState | none | void |
| MoveToTargetAct | TargetActor: AActor* | void |
| StartSleep | Duration: float | void |
| SetSprinting | sprinting?: bool | void |
| TickTeamName | none | void |
| DoorCheck | none | void |
| MoveToThenInteract | TargetActor: AActor* | void |
| MakePing | pingID: int32, Loc: FVector | void |
| PingShootTarget | none | void |
| SpotItems | none | void |
| PingItem | item: AActor* | void |
| AddAiChat | robber?: bool, Message: FString, playerAI: APlayerAI_C* | void |
| StartLadderSleepAll | Duration: float, spline: USplineComponent*, down?: bool | void |
| LadderTick | none | void |
| LadderFin | none | void |
| ZeroPitch | none | void |
| Flashed | none | void |
| CloseDoor | door: ADoorAct_C* | void |
| InitVars | none | void |
| DoorCloseLookAt | none | void |
| AiDied | none | void |
| BoxDmg | none | void |
| TickBoxing | none | void |
| BoxOnceSV | none | void |
| DiedEvent | none | void |
| Tasered | Duration: float | void |
| SupriseRespawnAll | none | void |
| interactfin | none | void |
| RespawnCopTimer | none | void |
| SlowDownTimeSV | CustomTimeDilation: float | void |
| SlowDownTimeALL | CustomTimeDilation: float | void |
| ForceWalkFW | none | void |
| RecentlyAttackedByDog | dog: APolice_Dog_C* | void |
| StartWalkForward | none | void |
| OnMoveToInteractFailed | none | void |
| RecentlyRespawned | none | void |
| SupriseRespawnSV | NewLocation: FVector | void |

---

## PlayerAI_Cop
**Inheritance:** `PlayerAI_Cop → PlayerAI → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| targetPlayer | Object |
| IgnoreActs | Array |
| susSoundLoc | FVector |
| lastSpottedUTC | FDateTime |
| alreadyinteracted | Array |
| moneyStolen? | Bool (Replicated) |
| backupCop | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool | FText |
| ignoreDistanceChecks | none | bool |
| InteractSV | PlayerChar: APlayerChar_C*, CallFunc_Add_IntInt_ReturnValue: int32 | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| SetMat | K2Node_SwitchInteger_CmpSuccess: bool | void |
| UserConstructionScript | none | void |
| SetState | none | void |
| AI_SuspiciousSound | susSoundLoc: FVector, shortSound?: bool | void |
| SpotItems | none | void |

---

## PlayerAI_Rob
**Inheritance:** `PlayerAI_Rob → PlayerAI → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| DeadBodyDrop | Object |
| BombBag | Object |
| MoneyFX | Object |
| MoneyBag | Object |
| rope | Object |
| hasBombBag? | Bool (Replicated) |
| moneyAmount | Int (Replicated) |
| heartRatePlayer | Object (Replicated) |
| roped? | Bool (Replicated) |
| clothingID | Int (Replicated) |
| CurrentZone | TEnumAsByte<ZoneEnum> |
| moneyBagShouldBeActive? | Bool |
| noNeedToDisguise | Array |
| recentlySus? | Bool |
| InterTargetBeforeBox | Object |
| spawnLoc | Object (Replicated) |
| dontSetMesh? | Bool |
| doorTries | Int |
| safed | Object |
| oldLoc | FVector |
| lastDebugPrint | String |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| debugPrint | InString: FString | void |
| UserConstructionScript | CallFunc_K2_SetRelativeLocation_SweepHitResult: FHitResult, CallFunc_K2_AttachToComponent_ReturnValue: bool, CallFunc_K2_AttachToComponent_ReturnValue_1: bool | void |
| CheckUnrope | none | void |
| SetState | none | void |
| DropBombBagSV | none | void |
| DropMoneyBagSV | none | void |
| ChainMoney | none | void |
| CheckRobSprint | none | void |
| SetRecentFishyAction | none | void |
| FindRescueVan | none | void |
| DiedEvent | none | void |
| CheckBag | none | void |
| TryGrabMoney | none | void |
| SetState_HasFittingClothes | none | void |
| SetState_FindRescueVan | none | void |
| SetState_FindRandomInteract | none | void |
| SetState_FocusVaultDoors | none | void |
| SetState_FocusEasyMoney | none | void |
| SetState_HasNoBombBag | none | void |
| OnMoveToInteractFailed | none | void |
| SetState_RobBotStuck | none | void |

---

## PaintMoneyBag
**Inheritance:** `PaintMoneyBag → Actor`

### Variables
| Name | Type |
|------|------|
| Widget1 | Object |
| Widget | Object |
| StaticMesh | Object |
| DefaultSceneRoot | Object |
| moneyValue | Int (Replicated) |
| dontExplode | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetAiInteractTraceLocation | none | FVector |
| PlayerAiCanInteract | none | bool |
| PlayerAiInteract | playerai: APlayerAI_C*, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Add_IntInt_ReturnValue: int32 | bool |
| PlayerAiInteractTimer | playerai: APlayerAI_C* | float |
| GetAiInteractWorldLoc | none | FVector |
| CopInter? | none | bool |
| GetItemName | none | FString |
| RefreshPhysics | none | bool |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C*, CallFunc_GetPlayerPawn_ReturnValue: APawn*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_SelectFloat_ReturnValue: float | bool |
| RefreshPhys | none | void |
| TickVis | none | void |
| DontAll | none | void |

---

## FEDHologram
**Inheritance:** `FEDHologram → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| SM_Prop_Kettle_01_Base_01 | Object |
| Sphere | Object |
| Box | Object |
| StaticMesh | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool | FText |
| GotDamagedBy | player: APlayerChar_C*, local: FVector | void |
| AiBlockFix | none | void |

---

## WeaponCrate
**Inheritance:** `WeaponCrate → Actor`

### Variables
| Name | Type |
|------|------|
| Widget3 | Object |
| Widget2 | Object |
| Widget1 | Object |
| StaticMesh1 | Object |
| Widget | Object |
| StaticMesh | Object |
| DefaultSceneRoot | Object |
| weaponID | Int (Replicated) |
| chuteGone? | Bool (Replicated) |
| attached? | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| Refresh | none | void |
| TickVis | none | void |
| detach | Target: USceneComponent* | void |
| attach | none | void |

---

## SmartCCTV
**Inheritance:** `SmartCCTV → CCTV → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| StaticMesh3 | Object |
| players_0 | Array |
| alert | Bool (Replicated) |
| ebox | Object |
| bonus? | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| SmartTick | none | void |
| GetRobbers | none | void |
| startalert | none | void |

---

## CctvSmart
**Inheritance:** `CctvSmart → CCTV → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| StaticMesh4 | Object |
| StaticMesh3 | Object |
| alert | Bool |
| ebox | Object |
| bonus? | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| SmartTick | none | void |
| startalert | none | void |

---

## CautionBarrier
**Inheritance:** `CautionBarrier → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Plane5 | Object |
| Plane4 | Object |
| Plane3 | Object |
| Plane2 | Object |
| Plane1 | Object |
| Plane | Object |
| StaticMesh1 | Object |
| Box | Object |
| StaticMesh | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool | FText |
| AiBlockFix | none | void |
| UpdateCollisions | none | void |

---

## HasStation
**Inheritance:** `HasStation → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Box | Object |
| Niagara1 | Object |
| StaticMesh5 | Object |
| Niagara | Object |
| StaticMesh2 | Object |
| ChildActor1 | Object |
| ChildActor | Object |
| StaticMesh | Object |
| tasering? | Bool (Replicated) |
| recentlyTasered? | Bool |
| emp? | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| EmpStart | duration: float | bool |
| RobberTick | none | void |
| StartTaser | act: AActor* | void |
| EmpBegin | Duration: float | void |
| AiBlockFix | none | void |

---

## DrillBag
**Inheritance:** `DrillBag → Actor`

### Variables
| Name | Type |
|------|------|
| Widget | Object |
| StaticMesh | Object |
| DefaultSceneRoot | Object |
| dontdraw | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetAiInteractTraceLocation | none | FVector |
| PlayerAiCanInteract | none | bool |
| PlayerAiInteract | playerai: APlayerAI_C*, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_HasAuthority_ReturnValue: bool | bool |
| PlayerAiInteractTimer | playerai: APlayerAI_C* | float |
| GetAiInteractWorldLoc | none | FVector |
| CopInter? | none | bool |
| GetItemName | none | FString |
| RefreshPhysics | none | bool |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| GetCustomTrace | none | FHitResult |
| GetCustomPingSettings | Executor: APawn* | TArray |
| RefreshPhys | none | void |
| TickVis | none | void |

---

## BarbedWire
**Inheritance:** `BarbedWire → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Sphere | Object |
| ChildActor | Object |
| StaticMesh | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | FText |
| ignoreDistanceChecks | none | bool |
| InteractSV | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| dmg | none | void |
| AiBlockFix | none | void |

---

## ThrowedGrenade_Coin
**Inheritance:** `ThrowedGrenade_Coin → Actor`

### Variables
| Name | Type |
|------|------|
| Box | Object |
| ProjectileMovement | Object |
| StaticMesh | Object |
| playedSound | Bool |
| npcs | Int |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## MoneyPrinter
**Inheritance:** `MoneyPrinter → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Widget | Object |
| drop | Object |
| SM_Prop_Poster_Stocks_01 | Object |
| SM_Prop_Poster_03 | Object |
| SM_Prop_Money_Note_05 | Object |
| SM_Prop_Money_Note_04 | Object |
| SM_Prop_Money_Note_03 | Object |
| SM_Prop_Money_Note_02 | Object |
| SM_Prop_Money_Note_01 | Object |
| SM_Prop_Computer_Printer_Paper_01 | Object |
| StaticMesh | Object |
| robber? | Bool (Replicated) |
| cryptoProgress | Float (Replicated) |
| oldProgress | Float |
| sound | Object |
| oldPassiveScore | Int |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool | FText |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| Print | none | void |
| ProgressTick | none | void |
| ReviveAll | none | void |

---

## HpKit
**Inheritance:** `HpKit → Actor`

### Variables
| Name | Type |
|------|------|
| BaseMesh | Object |
| DefaultSceneRoot | Object |
| interactName | String |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C* | FText |
| ignoreDistanceChecks | none | bool |
| InteractSV | PlayerChar: APlayerChar_C*, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FClamp_ReturnValue: float | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |

---

## HpKit_Donut
**Inheritance:** `HpKit_Donut → HpKit → Actor`

### Variables
| Name | Type |
|------|------|

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## DestrWindowVentSoundSTRONG
**Inheritance:** `DestrWindowVentSoundSTRONG → Actor`

### Variables
| Name | Type |
|------|------|
| MIddle | Object |
| Destructible | Object |
| Box | Object |
| DefaultSceneRoot | Object |
| destroyed | Bool (Replicated) |
| DamageRadius | Float |
| ImpulseStrength | Float |
| BaseDmg | Float |
| cut | Bool (Replicated) |
| hp | Float |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractSV | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| CanBePenetrated? | inputDmg: float, CallFunc_Greater_FloatFloat_ReturnValue: bool | float |
| bulletsCanDmg? | helper: bool | bool |
| DestroyWall | Target: AActor*, sound: bool | void |
| ResetMesh | none | void |

---

## JokerCard
**Inheritance:** `JokerCard → Actor`

### Variables
| Name | Type |
|------|------|
| Plane | Object |
| Cube | Object |
| DefaultSceneRoot | Object |
| lastPinger | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_Not_PreBool_ReturnValue: bool | FText |
| ignoreDistanceChecks | none | bool |
| InteractSV | PlayerChar: APlayerChar_C*, NewLocalVar_0: FTransform | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| StartPinging | none | void |
| PingTick | none | void |

---

## PoisonSmoke
**Inheritance:** `PoisonSmoke → Actor`

### Variables
| Name | Type |
|------|------|
| ParticleSystem | Object |
| Sphere | Object |
| DefaultSceneRoot | Object |
| dmg | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| dmgtick | none | void |

---

## ShieldBubble
**Inheritance:** `ShieldBubble → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Plane | Object |
| Niagara | Object |
| StaticMesh2 | Object |
| Cylinder | Object |
| hexbase | Object |
| hexsphere | Object |
| shieldmat | Object |
| hpRepl | Float (Replicated) |
| emp? | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| EmpStart | duration: float | bool |
| heal | none | void |
| ReplDmg | none | void |
| EmpBegin | Duration: float | void |

---

## AI_VIP
**Inheritance:** `AI_VIP → AI_Base → AI_Char → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| FX_PoisonedSmoke | Object |
| teamnameWidget | Object |
| poisoned? | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| getPaintingValue | easel: ACanvasEasel_C* | FVector |
| TimerAlt | none | bool |
| GetAltInteractName | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | FText |
| TickTeamName | none | void |
| heal | none | void |

---

## PaperPlane
**Inheritance:** `PaperPlane → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| Camera | Object |
| SpringArm | Object |
| CAR_ENGINE_i6_3L_4000_RPM_loop_mono | Object |
| muzzle | Object |
| StaticMesh | Object |
| Capsule | Object |
| SixDOFMovement | Object |
| small_airplane_Body9 | Object |
| SM_Prop_WallCamera_02_Camera_01 | Object |
| small_airplane_Body8 | Object |
| propeller | Object |
| small_airplane_Body6 | Object |
| small_airplane_Body5 | Object |
| small_airplane_Body4 | Object |
| pro | Object |
| small_airplane_Body2 | Object |
| small_airplane_Body1 | Object |
| small_airplane_Body | Object |
| LastPossessedPlayer | Object |
| hp | Float (Replicated) |
| DroneHUD | Object |
| fw | Float |
| shooting? | Bool (Replicated) |
| improvedSpeed? | Bool (Replicated) |
| hasWeapons? | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| getPaintingValue | easel: ACanvasEasel_C* | FVector |
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| PropellerTick | none | void |
| TellClPossessed | none | void |
| WantsUnpossessCl | none | void |
| WantsUnpossessSV | none | void |
| TellClGotUnpos | none | void |
| MoveForward | none | void |
| SetShootingSV | shooting?: bool | void |
| ShootTick | none | void |
| HitSV | act: AActor*, relLoc: FVector | void |
| ForceSpec | none | void |
| ShootForce | none | void |

---

## DestrWall2
**Inheritance:** `DestrWall2 → Actor`

### Variables
| Name | Type |
|------|------|
| DmgCheckPoint | Object |
| StaticMesh1 | Object |
| StaticMesh | Object |
| Scene1ins | Object |
| SceneOuts | Object |
| AI_Box | Object |
| NavModifier | Object |
| RocketTarget1 | Object |
| RocketTarget | Object |
| Box | Object |
| DestructibleInt | Object |
| Destructible | Object |
| DefaultSceneRoot | Object |
| destroyed | Bool (Replicated) |
| armorInside? | Bool (Replicated) |
| armorOutside? | Bool (Replicated) |
| armorOutsideHp | Float |
| armorInsideHp | Float |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| CanBePenetrated? | inputDmg: float | float |
| bulletsCanDmg? | helper: bool | bool |
| CheckTargetVis | none | void |
| PlacementTick | inside?: bool | void |
| DestroyWall | Target: AActor* | void |
| Undestroy | none | void |
| ResetDestr | none | void |

---

## DestrWall3
**Inheritance:** `DestrWall3 → Actor`

### Variables
| Name | Type |
|------|------|
| DmgCheckPoint | Object |
| StaticMesh1 | Object |
| StaticMesh | Object |
| Scene1ins | Object |
| SceneOuts | Object |
| AI_Box | Object |
| NavModifier | Object |
| RocketTarget1 | Object |
| RocketTarget | Object |
| Box | Object |
| DestructibleInt | Object |
| Destructible | Object |
| DefaultSceneRoot | Object |
| destroyed | Bool (Replicated) |
| armorInside? | Bool (Replicated) |
| armorOutside? | Bool (Replicated) |
| armorOutsideHp | Float |
| armorInsideHp | Float |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| CanBePenetrated? | inputDmg: float | float |
| bulletsCanDmg? | helper: bool | bool |
| CheckTargetVis | none | void |
| PlacementTick | inside?: bool | void |
| DestroyWall | Target: AActor* | void |
| Undestroy | none | void |
| ResetDestr | none | void |

---

## DestrWall4
**Inheritance:** `DestrWall4 → Actor`

### Variables
| Name | Type |
|------|------|
| DmgCheckPoint | Object |
| StaticMesh1 | Object |
| StaticMesh | Object |
| Scene1ins | Object |
| SceneOuts | Object |
| AI_Box | Object |
| NavModifier | Object |
| RocketTarget1 | Object |
| RocketTarget | Object |
| Box | Object |
| DestructibleInt | Object |
| Destructible | Object |
| DefaultSceneRoot | Object |
| destroyed | Bool (Replicated) |
| armorInside? | Bool (Replicated) |
| armorOutside? | Bool (Replicated) |
| armorOutsideHp | Float |
| armorInsideHp | Float |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| CanBePenetrated? | inputDmg: float | float |
| bulletsCanDmg? | helper: bool | bool |
| CheckTargetVis | none | void |
| PlacementTick | inside?: bool | void |
| DestroyWall | Target: AActor* | void |
| Undestroy | none | void |
| ResetDestr | none | void |

---

## WaterPuddle
**Inheritance:** `WaterPuddle → Actor`

### Variables
| Name | Type |
|------|------|
| ChildActor | Object |
| Sphere | Object |
| NavModifier | Object |
| SM_Prop_Water_Puddle_01 | Object |
| DefaultSceneRoot | Object |
| decay | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| RetryNav | none | void |

---

## Trampoline
**Inheritance:** `Trampoline → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| StaticMesh | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |

---

## ReviveKit
**Inheritance:** `ReviveKit → Actor`

### Variables
| Name | Type |
|------|------|
| Decal3 | Object |
| Decal2 | Object |
| Decal1 | Object |
| Decal | Object |
| StaticMesh | Object |
| Sphere | Object |
| Widget | Object |
| throwForce | FVector |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| RefreshPhysics | none | bool |
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_canCarryBombs__can_: bool | FText |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| InteractSV | PlayerChar: APlayerChar_C*, OldPlayerMat: UMaterialInterface*, OldPlayerMesh: USkeletalMesh*, CallFunc_canCarryBombs__can_: bool | bool |
| help2 | NewParam: bool | void |
| helper | z: TEnumAsByte<ZoneEnum>, CallFunc_EqualEqual_ByteByte_ReturnValue: bool | bool |
| RefreshPhys | none | void |
| TickVis | none | void |

---

## SpyDrone
**Inheritance:** `SpyDrone → TechDrone → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## Money_Diamond
**Inheritance:** `Money_Diamond → MoneyBaseAct → Actor`

### Variables
| Name | Type |
|------|------|
| Widget | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| TickVis | none | void |

---

## SyringeBullet
**Inheritance:** `SyringeBullet → Actor`

### Variables
| Name | Type |
|------|------|
| Niagara | Object |
| StaticMesh | Object |
| Scene | Object |
| StaticMesh1 | Object |
| ProjectileMovement | Object |
| OldLoc | FVector |
| serum? | Bool |
| dontDMG | Bool |
| clientOnly? | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| HitScan | none | void |
| SetSyringeDecal | loc: FVector | void |

---

## BloodDecal
**Inheritance:** `BloodDecal → Actor`

### Variables
| Name | Type |
|------|------|
| Decal | Object |
| DefaultSceneRoot | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## Police_Dog
**Inheritance:** `Police_Dog → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| teamnameWidget | Object |
| Niagara | Object |
| StaticMesh2 | Object |
| Unreal_SK_Chr_Attach_Vest_Police_Shepherd_01 | Object |
| YawChangeAvg | Float |
| OldYaw | Float |
| lookAtTarget | Object |
| afk | Bool (Replicated) |
| lastMoveTime | Float |
| moveToOwner? | Bool |
| robTarget | Object |
| biteCD | Bool |
| tasered? | Bool (Replicated) |
| HP | Float (Replicated) |
| sniff | FTimerHandle |
| sniffobj | Object |
| followOwner? | Bool (Replicated) |
| moveOwner | Object |
| sniffFollowing? | Bool |
| vestHP | Float (Replicated) |
| dontChaseHim | Object |
| fastUnAFK | Bool |
| movFails | Int |
| sniffDecayTime | Float |
| SniffTimeoutTimer | FTimerHandle |
| Doors | Array |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| getPaintingValue | easel: ACanvasEasel_C* | FVector |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| Taser | secs: float | bool |
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| TryStopSniffing | CallFunc_GetAnimInstance_ReturnValue: UAnimInstance*, CallFunc_Montage_IsPlaying_ReturnValue: bool, CallFunc_K2_IsValidTimerHandle_ReturnValue: bool | void |
| CheckTurnAnim | none | void |
| MoveToOwner | TargetActor: AActor* | void |
| SetLookAtTarget | lookAtTarget: AActor*, duration: float | void |
| UnAfk | fast: bool | void |
| WatchRobs | none | void |
| BitePlayer | none | void |
| BitePlayerALL | none | void |
| TaseredSV | Duration: float | void |
| GoSniffDead | ragdollspawn: AActor* | void |
| SniffALL | none | void |
| SniffSucc | none | void |
| BarkALL | none | void |
| ConfusedALL | none | void |
| SetFollowMode | followOwner?: bool, TargetActor: AActor* | void |
| MaybeMoveAgainOwner | none | void |
| TickTeamName | none | void |
| RegenHP | none | void |
| NoLongerFollwingOwner | none | void |
| DoorCheck | none | void |
| InitVars | none | void |
| SlowDownTimeSV | none | void |
| SlowDownTimeALL | none | void |

---

## DogRagdoll
**Inheritance:** `DogRagdoll → Actor`

### Variables
| Name | Type |
|------|------|
| Widget | Object |
| SkeletalMesh | Object |
| DefaultSceneRoot | Object |
| PoseSnap | FPoseSnapshot |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_isClass__is_: bool, CallFunc_IsValid_ReturnValue: bool | FText |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| RestartSV | none | bool |
| RestartCl | none | bool |

---

## BloodDecalSmall
**Inheritance:** `BloodDecalSmall → Actor`

### Variables
| Name | Type |
|------|------|
| Decal | Object |
| DefaultSceneRoot | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## ConveyerBelt
**Inheritance:** `ConveyerBelt → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| BagMagnetBox | Object |
| MoveBoxJump | Object |
| Audio | Object |
| SM_Prop_Desk_Treadmill_02 | Object |
| AntiJumpBox | Object |
| Box1 | Object |
| Scene | Object |
| MoveBox | Object |
| SM_Prop_Desk_Treadmill_01 | Object |
| touchedBags | Array |
| debug | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| DebugPrint | InString: FString | void |

---

## XrayScreen
**Inheritance:** `XrayScreen → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Cube3 | Object |
| Cube2 | Object |
| Cube1 | Object |
| Cube | Object |
| Plane | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## TimeSlower
**Inheritance:** `TimeSlower → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| AMBIENCE_SCI_FI_Large_Space_Hangar_Deep_Smooth_loop_stereo | Object |
| Box | Object |
| SM_Bld_Corp_Generator_01_Preset_01 | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | FText |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| ignoreDistanceChecks | none | bool |

---

## ChronoGrenade
**Inheritance:** `ChronoGrenade → Actor`

### Variables
| Name | Type |
|------|------|
| Damage | Object |
| Capsule | Object |
| StaticMesh | Object |
| ProjectileMovement | Object |
| client? | Bool |
| LastVel | FVector |
| hitAct | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## RoyalCrown
**Inheritance:** `RoyalCrown → Actor`

### Variables
| Name | Type |
|------|------|
| CrownMesh | Object |
| DefaultSceneRoot | Object |
| queen | Object (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C* | FText |
| ignoreDistanceChecks | none | bool |
| InteractSV | PlayerChar: APlayerChar_C*, CallFunc_Add_IntInt_ReturnValue: int32 | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| UserConstructionScript | CallFunc_IsValid_ReturnValue: bool | void |
| Attach | none | void |

---

## RumBag
**Inheritance:** `RumBag → Actor`

### Variables
| Name | Type |
|------|------|
| StaticMesh | Object |
| Widget | Object |
| throwForce | FVector |
| lastToucher | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetAiInteractTraceLocation | none | FVector |
| PlayerAiCanInteract | none | bool |
| PlayerAiInteract | playerai: APlayerAI_C*, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_HasAuthority_ReturnValue: bool | bool |
| PlayerAiInteractTimer | playerai: APlayerAI_C* | float |
| GetAiInteractWorldLoc | none | FVector |
| CopInter? | none | bool |
| GetItemName | none | FString |
| RefreshPhysics | none | bool |
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | FText |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| InteractSV | PlayerChar: APlayerChar_C*, OldPlayerMat: UMaterialInterface*, OldPlayerMesh: USkeletalMesh* | bool |
| GetCustomTrace | none | FHitResult |
| GetCustomPingSettings | Executor: APawn* | TArray |
| RefreshPhys | none | void |
| TickVis | none | void |

---

## CaponeTunnel
**Inheritance:** `CaponeTunnel → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Widget | Object |
| Audio | Object |
| SM_Env_Dirt_Pile_04 | Object |
| SM_Prop_Pipe_Concrete_06 | Object |
| SM_Prop_Pipe_Concrete_05 | Object |
| SM_Prop_Pipe_Concrete_04 | Object |
| SM_Prop_Pipe_Concrete_03 | Object |
| SK_Veh_Excavator_02_Auger_01 | Object |
| SM_Prop_Pipe_Concrete_02 | Object |
| TpScene3 | Object |
| TpScene2 | Object |
| TpScene1 | Object |
| Box | Object |
| SM_Prop_Barrel_04 | Object |
| SM_Prop_Barrel_03 | Object |
| SM_Prop_Barrel_02 | Object |
| SM_Env_Dirt_Pile_03 | Object |
| SM_Env_Dirt_Pile_02 | Object |
| SM_Env_Dirt_Pile_01 | Object |
| SM_Prop_Ladder_Tied_01 | Object |
| SM_Prop_Well_Plinth_01 | Object |
| TpScene | Object |
| SM_Prop_Path_Brick_09 | Object |
| SM_Prop_Path_Brick_08 | Object |
| SM_Prop_Path_Brick_07 | Object |
| SM_Prop_Path_Brick_06 | Object |
| SM_Prop_Path_Brick_05 | Object |
| SM_Prop_Path_Brick_04 | Object |
| SM_Prop_Path_Brick_03 | Object |
| SM_Prop_Path_Brick_02 | Object |
| Plane | Object |
| Inst | Object |
| upSize | Float |
| partner | Object (Replicated) |
| finished? | Bool (Replicated) |
| DrillTimerSV | FTimerHandle |
| running? | Bool (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C*, CallFunc_GetDistanceTo_ReturnValue: float, CallFunc_MapRangeClamped_ReturnValue: float | bool |
| FinishedDrill | none | void |
| SetDrillDone | none | void |
| TickVis | none | void |

---

## RomanGuard
**Inheritance:** `RomanGuard → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| Box | Object |
| shieldcol | Object |
| RiotShieldTP | Object |
| StaticMesh | Object |
| YawChangeAvg | Float |
| OldYaw | Float |
| HP | Float |
| DeathInfo | FDeathInfo__pf1458230002 |
| target | Object |
| attackCD | Bool |
| failcounter | Int |
| ogTrans | FTransform |
| movingBack? | Bool |
| lastHitTime | Float |
| Doors | Array |
| shieldDown? | Bool (Replicated) |
| friendlies | Array |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| UserConstructionScript | CallFunc_K2_AttachToComponent_ReturnValue: bool, CallFunc_K2_AttachToComponent_ReturnValue_1: bool | void |
| CheckTurnAnim | none | void |
| DestroyHandle | none | void |
| StartChase | none | void |
| AttackTick | none | void |
| AttackALL | none | void |
| StartAttackSV | none | void |
| ShieldSoundALL | none | void |
| DoorCheck | none | void |
| OnBoxOverlap | OverlappedComponent: UPrimitiveComponent*, OtherActor: AActor*, OtherComp: UPrimitiveComponent*, OtherBodyIndex: int32, bFromSweep: bool, SweepResult: FHitResult | void |
| OnBoxEndOverlap | OverlappedComponent: UPrimitiveComponent*, OtherActor: AActor*, OtherComp: UPrimitiveComponent*, OtherBodyIndex: int32 | void |

---

## BulletReflection
**Inheritance:** `BulletReflection → Actor`

### Variables
| Name | Type |
|------|------|
| ProjectileMovement | Object |
| Niagara | Object |
| StaticMesh | Object |
| DefaultSceneRoot | Object |
| lastV | FVector |
| Dmg | Float |
| sv? | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## CanvasEasel
**Inheritance:** `CanvasEasel → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Scene | Object |
| SceneCaptureComponent2D_Color | Object |
| SceneCaptureComponent2D_Pencil | Object |
| StaticMesh | Object |
| CanvasMI | Object |
| CanvasRT_Pencil | Object |
| CanvasRT_Color | Object |
| canvasWorld | Object (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| CapturePainting | none | void |

---

## Money_Canvas
**Inheritance:** `Money_Canvas → MoneyBaseAct → Actor`

### Variables
| Name | Type |
|------|------|
| Widget | Object |
| Box | Object |
| Plane | Object |
| StaticMesh1 | Object |
| CanvasMI | Object |
| ProgressSV | Float (Replicated) |
| localProgress | Float |
| falling? | Bool (Replicated) |
| paintingName | FText (Replicated) |
| baseMoneyValue | Int |
| painter | Object (Replicated) |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| TimerAlt | none | bool |
| ignoreDistanceChecks | none | bool |
| InitPainting | canvasRtPencil: UTexture*, canvasRtColor: UTexture* | void |
| StartFalling | none | void |
| PaintSoundALL | none | void |
| PainterDeadTick | none | void |
| InitWidget | none | void |
| TickVis | none | void |

---

## WaterSteamer
**Inheritance:** `WaterSteamer → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| collBox | Object |
| Box | Object |
| ParticleSystem | Object |
| StaticMesh | Object |
| active? | Bool (Replicated) |
| s | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | FText |
| InteractSV | PlayerChar: APlayerChar_C* | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| ignoreDistanceChecks | none | bool |
| HealTick | none | void |
| SetActiveAgain | none | void |

---

## TennisBallMachine
**Inheritance:** `TennisBallMachine → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| tb30 | Object |
| tb29 | Object |
| tb28 | Object |
| tb27 | Object |
| tb26 | Object |
| tb25 | Object |
| tb24 | Object |
| tb23 | Object |
| tb22 | Object |
| tb21 | Object |
| tb20 | Object |
| tb19 | Object |
| tb18 | Object |
| tb17 | Object |
| tb16 | Object |
| tb15 | Object |
| tb9 | Object |
| tb14 | Object |
| tb13 | Object |
| tb12 | Object |
| tb11 | Object |
| tb10 | Object |
| tb8 | Object |
| tb7 | Object |
| tb6 | Object |
| tb5 | Object |
| tb4 | Object |
| tb3 | Object |
| tb2 | Object |
| tb1 | Object |
| PS_Muzzle_Sparks_02 | Object |
| muzzle | Object |
| navBlock | Object |
| StaticMesh | Object |
| remainingBalls | Int (Replicated) |
| sortedBalls | Array |
| f | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | FText |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| ignoreDistanceChecks | none | bool |
| ShootBall | none | void |
| SortBalls | none | void |

---

## TennisBall_Projectile
**Inheritance:** `TennisBall_Projectile → Actor`

### Variables
| Name | Type |
|------|------|
| ProjectileMovement | Object |
| StaticMesh | Object |
| Sphere | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## SwarmDrone_Base
**Inheritance:** `SwarmDrone_Base → TechDrone → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| InworldWidget | Object |
| DroneName | Object |
| PointLight | Object |
| StaticMesh1 | Object |
| StaticMesh | Object |
| ColorMatInst | Object |
| color | FLinearColor |
| destroyed? | Bool (Replicated) |
| name | FText |
| disableSound | Bool |
| forceMoveTo | FVector |
| moveCompleteTimer | FTimerHandle |
| projectedMoveTo | FVector |
| moveRetries | Int |
| moveToAnchor | FVector |
| switchMoveToOrder | Bool |
| prevMoveAnchor | FVector |
| moveToTickTarget | FVector |
| backUpTimer | FTimerHandle |
| backUpTimeoutTimer | FTimerHandle |
| moveToSuccTimer | FTimerHandle |
| movetoStartLoc | FVector |
| prevCheckMoveLoc | FVector |
| checkMoveSucc | Int |
| debug | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| InteractTimer | playerchar: APlayerChar_C* | bool |
| InteractSV | PlayerChar: APlayerChar_C*, CallFunc_isClass_is: bool, CallFunc_BooleanAND_ReturnValue: bool | bool |
| MotorNoiseTick | none | void |
| RepairSV | none | void |
| ForceMoveToLoc | forceMoveTo: FVector, forceMoveToAnchor: FVector | void |
| MoveToCompletionTick | none | void |
| StartMoveComplete | reason: FString | void |
| ForceMoveToRetry | forceMoveTo: FVector | void |
| FinishedReturningToNavPoint | none | void |
| ReturningToNavPointTimedOut | none | void |
| PostMoveToSucc | none | void |
| CheckMoveToSucc | none | void |
| BlockedBy | actor: AActor* | void |
| SweepMovementBlockedBy | act: AActor* | void |
| ReachedLocationSuccess | none | void |

---

## Sweepo
**Inheritance:** `Sweepo → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| Widget | Object |
| Sphere | Object |
| SM_Prop_Fire_Extinguisher_01 | Object |
| SpotLight | Object |
| SpotLight1 | Object |
| alarm | Object |
| background_hum_engine_motor_ambience_02_Cue | Object |
| PointLight | Object |
| FireExtinguisher_Cue | Object |
| Niagara | Object |
| SM_Item_Tape_01 | Object |
| plants | Array |
| currentPlant | Object (Replicated) |
| projectedMoveTo | FVector |
| movetoStartLoc | FVector |
| moving | Bool |
| firing? | Bool (Replicated) |
| randomMoving? | Bool |
| walkSpeedSlow? | Bool (Replicated) |
| HP | Float |
| Doors | Array |
| failCounter | TMap |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| EmpStart | duration: float, CallFunc_HasAuthority_ReturnValue: bool | bool |
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| FindFire | none | void |
| MoveToPlant | none | void |
| Rotate | none | void |
| Blink | none | void |
| DoorCheck | none | void |
| StartDoorCheck | none | void |
| InitVars | none | void |
| TickVis | none | void |
| InitWidget | none | void |
| GiveOwnerIdeaSpark | none | void |

---

## GrumpyMotionDetector
**Inheritance:** `GrumpyMotionDetector → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| muzzle | Object |
| Niagara1 | Object |
| SM_Veh_Heli_Attach_Minigun_FixedBarrel | Object |
| SM_Veh_Heli_Attach_Minigun_FixedBarrel1 | Object |
| NavModifier | Object |
| Box | Object |
| Niagara | Object |
| StaticMesh2 | Object |
| Capsule | Object |
| StaticMesh1 | Object |
| StaticMesh | Object |
| emp? | Bool (Replicated) |
| currentBarrel | Int |
| barrelPitch | Float |
| RPM | Float |
| shooting? | Bool (Replicated) |
| bulletSound | Object |
| shootTimer | FTimerHandle |
| forceHit | Object |
| lastHit | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool | FText |
| ignoreDistanceChecks | none | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| EmpStart | duration: float | bool |
| RefreshLaserLength | none | void |
| destroyedCl | none | void |
| EmpBegin | Duration: float | void |
| MinigunAnim | none | void |
| EventFiredShot | none | void |
| ShootTick | none | void |
| ShootForce | none | void |
| HitSV | act: AActor*, relLoc: FVector | void |
| StartShoot | none | void |
| overlapLaser | OverlappedComponent: UPrimitiveComponent*, OtherActor: AActor*, OtherComp: UPrimitiveComponent*, OtherBodyIndex: int32, bFromSweep: bool, SweepResult: FHitResult | void |

---

## HideoTron
**Inheritance:** `HideoTron → Destroyable_Base → Actor`

### Variables
| Name | Type |
|------|------|
| Sphere | Object |
| StaticMesh | Object |
| hiddenMoneys | Array |
| destroyed? | Bool |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| destroyedCl | CallFunc_HasAuthority_ReturnValue: bool | void |
| CloakTick | none | void |

---

## StunOTron
**Inheritance:** `StunOTron → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| PointLight1 | Object |
| Capsule1 | Object |
| Niagara2 | Object |
| SM_Prop_Laser_01 | Object |
| Capsule | Object |
| StaticMesh2 | Object |
| StaticMesh1 | Object |
| StaticMesh | Object |
| PointLight | Object |
| Niagara1 | Object |
| Niagara | Object |
| worldDirInput | FVector (Replicated) |
| recentlyBounced | Bool |
| recentlyTasered | Bool |
| HP | Float |
| maxArmLength | Float |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| EmpStart | duration: float, CallFunc_HasAuthority_ReturnValue: bool | bool |
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| TaserAll | none | void |
| LaserLength | none | void |

---

## MoneyXMAS
**Inheritance:** `MoneyXMAS → MoneyBaseAct → Actor`

### Variables
| Name | Type |
|------|------|

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| PlayerInteracted | player: APlayerChar_C*, CallFunc_GetController_ReturnValue: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool | void |

---

## SantaClaus
**Inheritance:** `SantaClaus → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| SM_Item_Bag_Attachment_01 | Object |
| Niagara | Object |
| s | Array |
| t | FVector |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool | bool |
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| UserConstructionScript | CallFunc_K2_AttachToComponent_ReturnValue: bool | void |
| RandomTeleport | none | void |
| TeleportMulti | prevLoc: FVector | void |

---

## MoneyXMAS_Physics
**Inheritance:** `MoneyXMAS_Physics → MoneyBaseAct → Actor`

### Variables
| Name | Type |
|------|------|

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| PlayerInteracted | player: APlayerChar_C*, CallFunc_GetController_ReturnValue: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool | void |

---

## Artist_Grafitti
**Inheritance:** `Artist_Grafitti → Actor`

### Variables
| Name | Type |
|------|------|
| Decal | Object |
| DefaultSceneRoot | Object |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|

---

## DeaddropBot
**Inheritance:** `DeaddropBot → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| Widget | Object |
| SM_Prop_Briefcase_Bomb_02 | Object |
| SM_Prop_Briefcase_Bomb_01 | Object |
| Sphere | Object |
| SkeletalMesh | Object |
| CAR_ENGINE_i6_3L_5500_RPM_loop_mono | Object |
| hiddenInside? | Bool (Replicated) |
| ActivatingTimer | FTimerHandle |
| frozenMovementSpeed | Bool (Replicated) |
| prevHiddenInside | Bool |
| BoomTarget | Object |
| Doors | Array |
| hp | Float |
| RandomMovDir | FVector |
| dontExplode | Bool |
| hiddenInsideTime | Float |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| isSus | CallFunc_Not_PreBool_ReturnValue: bool | bool |
| bulletsCanDmg? | helper: bool | bool |
| CanBePenetrated? | inputDmg: float | float |
| UserConstructionScript | CallFunc_K2_AttachToComponent_ReturnValue: bool, CallFunc_K2_AttachToComponent_ReturnValue_1: bool | void |
| StartNearbyChecks | none | void |
| CheckNearbyTick | none | void |
| Spotted | none | void |
| StartActivating | none | void |
| ActivatingFinished | none | void |
| SetMovementSpeedFrozen | Frozen: bool | void |
| SoundTick | none | void |
| StartPathfindingToVault | reason: FString | void |
| DoorCheck | none | void |
| InitVars | none | void |
| StartDoorCheck | none | void |
| NoValidPaths | none | void |
| RandomMoveTick | none | void |
| StartRecheckPath | none | void |
| RecheckPath | none | void |
| NeedsToRepath | none | void |
| TickVis | none | void |
| InitWidget | none | void |
| JammedSV | none | void |
| DontExplodeMulti | none | void |

---

## PushableCart_Base
**Inheritance:** `PushableCart_Base → Character → Pawn → Actor`

### Variables
| Name | Type |
|------|------|
| Sphere | Object |
| SM_Prop_GoldPile_01 | Object |
| SM_Prop_Warehouse_Platform_Trolley_01 | Object |
| money | Int |
| CurrentMovDir | FVector |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| TimerAlt | none | bool |
| GetAltInteractName | PlayerChar: APlayerChar_C* | FText |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| ignoreDistanceChecks | none | bool |
| GetInteractName | PlayerChar: APlayerChar_C* | FText |
| StartPushInDir | dir: FVector | void |

---

## BP_LuaActor
**Inheritance:** `BP_LuaActor → Actor`

### Variables
| Name | Type |
|------|------|
| DefaultSceneRoot | Object |
| LuaFileName | String (Replicated) |
| ReplicatedVars | Array (Replicated) |
| LocalVars | Array |
| InteractionTimer | Float |
| InteractionString | String |
| bCanInteract | Bool |
| componentMap | TMap |

### Functions
| Name | Parameters | Returns |
|------|------------|---------|
| GetInteractName | PlayerChar: APlayerChar_C*, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_getHeistGS_gs: AHeistGS_C*, CallFunc_getHeistGS_gs_1: AHeistGS_C* | FText |
| InteractSV | PlayerChar: APlayerChar_C*, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_getHeistGS_gs: AHeistGS_C*, CallFunc_Concat_StrStr_ReturnValue: FString | bool |
| InteractTimer | playerchar: APlayerChar_C* | bool |
| ignoreDistanceChecks | none | bool |
| GetModMeshComponent | ComponentName: FString, CallFunc_Map_Find_Value: USceneComponent*, CallFunc_Map_Find_ReturnValue: bool | UActorComponent* |
| GetLuaFileName | none | FString |
| CheckStartScript | none | void |
| AddModMeshComponent | ComponentName: FString, MeshFileName: FString, TextureFileName: FString | void |
| LuaTick | none | void |

---

