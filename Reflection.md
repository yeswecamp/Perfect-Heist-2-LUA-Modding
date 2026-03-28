# Reflection API Reference

This document lists all Blueprint-accessible variables and functions on game classes.
Access these through wrapped actors in Lua, e.g. `playerActor.Health` or `playerActor:SomeFunction()`

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
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool, blockbulletdmg?: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, dmg: float, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_3: bool, CallFunc_GetDisplayName_ReturnValue: FString, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_HasAuthority_ReturnValue: bool, CallFunc_GetDisplayName_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_Multiply_FloatFloat_ReturnValue: float, CallFunc_GetTransform_ReturnValue: FTransform, CallFunc_TransformLocation_ReturnValue: FVector, K2Node_DynamicCast_AsFEDHologram: AFEDHologram_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_GetTransform_ReturnValue_1: FTransform, CallFunc_VSize_ReturnValue: float, CallFunc_InverseTransformLocation_ReturnValue: FVector, CallFunc_LessEqual_FloatFloat_ReturnValue_1: bool, CallFunc_Multiply_FloatFloat_ReturnValue_1: float, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_SelectFloat_ReturnValue: float, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_GreaterEqual_FloatFloat_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float | void |
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
| ClassID | uint8 (Replicated) |
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
| getPaintingValue | easel: ACanvasEasel_C*, preventPaint: bool, paintingName: FText, paintingDescr: FText, value: int32, traceOffset: FVector, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_isClass_is: bool, CallFunc_Greater_IntInt_ReturnValue: bool | void |
| GetRadiation | loc: FVector, power: float | void |
| isSus | isSus?: bool, isSusEasy?: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_GetGameTimeSinceCreation_ReturnValue: float, CallFunc_SelectInt_ReturnValue: int32, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_isDisguised__ReturnValue: FText, CallFunc_isDisguised__disguised_: bool, CallFunc_isDisguised__movement_: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_NotEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanOR_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanAND_ReturnValue_4: bool, CallFunc_BooleanAND_ReturnValue_5: bool | void |
| Taser | secs: float, true: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_Subtract_IntInt_ReturnValue_1: int32, CallFunc_Greater_IntInt_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_Greater_IntInt_ReturnValue_2: bool, CallFunc_Add_IntInt_ReturnValue_1: int32, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_4: bool, CallFunc_Not_PreBool_ReturnValue_3: bool, Temp_int_Variable: int32, CallFunc_BooleanAND_ReturnValue_5: bool, CallFunc_BooleanAND_ReturnValue_6: bool, Temp_int_Variable_1: int32, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_7: bool, CallFunc_BooleanAND_ReturnValue_8: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_SelectFloat_ReturnValue: float, CallFunc_SelectFloat_ReturnValue_1: float | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_4: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_5: bool, CallFunc_Greater_IntInt_ReturnValue_2: bool, CallFunc_Not_PreBool_ReturnValue_3: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_6: bool, CallFunc_Not_PreBool_ReturnValue_4: bool, CallFunc_BooleanAND_ReturnValue_7: bool, CallFunc_BooleanAND_ReturnValue_8: bool, CallFunc_BooleanAND_ReturnValue_9: bool, CallFunc_Add_IntInt_ReturnValue: int32, K2Node_MakeStruct_FormatArgumentData: FFormatArgumentData, K2Node_MakeArray_Array: TArray, CallFunc_Format_ReturnValue: FText | void |
| RestartCl | true?: bool | void |
| RestartSV | true?: bool | void |
| ToggleThermal | on?: bool, true: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, prevVestHP: float, playerkiller: APlayerChar_C*, NegatedDmg: float, TrueDmg: float, CallFunc_NotEqual_ByteByte_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_NotEqual_ByteByte_ReturnValue_1: bool, CallFunc_NotEqual_ByteByte_ReturnValue_2: bool, CallFunc_NotEqual_ByteByte_ReturnValue_3: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_3: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_4: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_5: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_6: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_7: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_8: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_9: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_10: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_11: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_12: bool, CallFunc_BooleanOR_ReturnValue_1: bool, CallFunc_GetEnumeratorUserFriendlyName_ReturnValue: FString, CallFunc_EqualEqual_ByteByte_ReturnValue_13: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_14: bool, CallFunc_Conv_VectorToString_ReturnValue: FString, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess_1: bool, K2Node_DynamicCast_AsPlayer_Char_1: APlayerChar_C*, K2Node_DynamicCast_bSuccess_2: bool, K2Node_DynamicCast_AsPolice_Dog: APolice_Dog_C*, K2Node_DynamicCast_bSuccess_3: bool, K2Node_DynamicCast_AsHorse_Char: AHorseChar_C*, K2Node_DynamicCast_bSuccess_4: bool, K2Node_DynamicCast_AsPlayer_Char_2: APlayerChar_C*, K2Node_DynamicCast_bSuccess_5: bool, CallFunc_GetController_ReturnValue: AController*, CallFunc_GetController_ReturnValue_1: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess_6: bool, K2Node_DynamicCast_AsHeist_PC_1: AHeistPC_C*, K2Node_DynamicCast_bSuccess_7: bool, CallFunc_Add_IntInt_ReturnValue: int32, K2Node_DynamicCast_AsHorse_Char_1: AHorseChar_C*, K2Node_DynamicCast_bSuccess_8: bool, K2Node_DynamicCast_AsRemote_Turret: ARemoteTurret_C*, K2Node_DynamicCast_bSuccess_9: bool, CallFunc_GetOwner_ReturnValue: AActor*, K2Node_DynamicCast_AsPlayer_Char_3: APlayerChar_C*, K2Node_DynamicCast_bSuccess_10: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue_1: int32, K2Node_DynamicCast_AsPlayer_Char_4: APlayerChar_C*, K2Node_DynamicCast_bSuccess_11: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_15: bool, CallFunc_Subtract_IntInt_ReturnValue_1: int32, CallFunc_Greater_IntInt_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_16: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_17: bool, CallFunc_Add_IntInt_ReturnValue_2: int32, CallFunc_Add_IntInt_ReturnValue_3: int32, K2Node_DynamicCast_AsPlayer_Char_5: APlayerChar_C*, K2Node_DynamicCast_bSuccess_12: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_GetController_ReturnValue_2: AController*, CallFunc_BooleanAND_ReturnValue_3: bool, K2Node_DynamicCast_AsHeist_PC_2: AHeistPC_C*, K2Node_DynamicCast_bSuccess_13: bool, CallFunc_BooleanAND_ReturnValue_4: bool, CallFunc_BooleanAND_ReturnValue_5: bool, K2Node_DynamicCast_AsPolice_Dog_1: APolice_Dog_C*, K2Node_DynamicCast_bSuccess_14: bool, K2Node_DynamicCast_AsPlayer_Char_6: APlayerChar_C*, K2Node_DynamicCast_bSuccess_15: bool, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_BooleanAND_ReturnValue_6: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_BooleanOR_ReturnValue_2: bool, K2Node_DynamicCast_AsPlayer_AI: APlayerAI_C*, K2Node_DynamicCast_bSuccess_16: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, K2Node_DynamicCast_AsPlayer_Char_7: APlayerChar_C*, K2Node_DynamicCast_bSuccess_17: bool, K2Node_DynamicCast_AsPlayer_Char_8: APlayerChar_C*, K2Node_DynamicCast_bSuccess_18: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_18: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_BooleanAND_ReturnValue_7: bool, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Multiply_FloatFloat_ReturnValue: float, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_3: FString, Temp_int_Variable: int32, Temp_int_Variable_1: int32, Temp_int_Variable_2: int32, Temp_int_Variable_3: int32, Temp_int_Variable_4: int32, CallFunc_GreaterEqual_IntInt_ReturnValue: bool, Temp_int_Variable_5: int32, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_GreaterEqual_IntInt_ReturnValue_1: bool, CallFunc_HasAuthority_ReturnValue: bool, CallFunc_K2_GetActorRotation_ReturnValue: FRotator, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, CallFunc_K2_GetActorLocation_ReturnValue_2: FVector, CallFunc_FindLookAtRotation_ReturnValue: FRotator, CallFunc_Multiply_FloatFloat_ReturnValue_1: float, CallFunc_BreakRotator_Roll: float, CallFunc_BreakRotator_Pitch: float, CallFunc_BreakRotator_Yaw: float, CallFunc_Multiply_FloatFloat_ReturnValue_2: float, CallFunc_MakeRotator_ReturnValue: FRotator, CallFunc_Multiply_FloatFloat_ReturnValue_3: float, CallFunc_EqualEqual_RotatorRotator_ReturnValue: bool, CallFunc_Multiply_FloatFloat_ReturnValue_4: float, CallFunc_Conv_BoolToString_ReturnValue: FString, CallFunc_Divide_FloatFloat_ReturnValue: float, CallFunc_IsValid_ReturnValue: bool, CallFunc_EqualEqual_FloatFloat_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_19: bool, CallFunc_BooleanAND_ReturnValue_8: bool, K2Node_DynamicCast_AsPlayer_Char_9: APlayerChar_C*, K2Node_DynamicCast_bSuccess_19: bool, CallFunc_GetController_ReturnValue_3: AController*, CallFunc_BooleanAND_ReturnValue_9: bool, K2Node_DynamicCast_AsHeist_PC_3: AHeistPC_C*, K2Node_DynamicCast_bSuccess_20: bool, CallFunc_BooleanAND_ReturnValue_10: bool, CallFunc_Multiply_FloatFloat_ReturnValue_5: float, CallFunc_Divide_FloatFloat_ReturnValue_1: float, CallFunc_Add_IntInt_ReturnValue_4: int32, CallFunc_RandomFloatInRange_ReturnValue: float, CallFunc_RandomFloatInRange_ReturnValue_1: float, CallFunc_MakeRotator_ReturnValue_1: FRotator, CallFunc_K2_GetActorLocation_ReturnValue_3: FVector, CallFunc_FindLookAtRotation_ReturnValue_1: FRotator, CallFunc_Divide_FloatFloat_ReturnValue_2: float, CallFunc_MakeTransform_ReturnValue: FTransform, CallFunc_ComposeRotators_ReturnValue: FRotator, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_FinishSpawningActor_ReturnValue: ABulletReflection_C*, CallFunc_FTrunc_ReturnValue: int32, CallFunc_EqualEqual_ByteByte_ReturnValue_20: bool, CallFunc_Subtract_IntInt_ReturnValue_2: int32, CallFunc_Not_PreBool_ReturnValue_3: bool, CallFunc_Multiply_IntFloat_ReturnValue: float, CallFunc_GreaterEqual_FloatFloat_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_21: bool, CallFunc_BooleanAND_ReturnValue_11: bool, CallFunc_BooleanAND_ReturnValue_12: bool, CallFunc_EqualEqual_FloatFloat_ReturnValue_1: bool, CallFunc_Multiply_FloatFloat_ReturnValue_6: float, CallFunc_GetObjectClass_ReturnValue: UClass*, CallFunc_EqualEqual_ClassClass_ReturnValue: bool, CallFunc_GetOwner_ReturnValue_1: AActor*, CallFunc_Not_PreBool_ReturnValue_4: bool, K2Node_DynamicCast_AsPlayer_Char_10: APlayerChar_C*, K2Node_DynamicCast_bSuccess_21: bool, K2Node_DynamicCast_AsPlayer_Char_11: APlayerChar_C*, K2Node_DynamicCast_bSuccess_22: bool, CallFunc_Multiply_FloatFloat_ReturnValue_7: float, Temp_int_Variable_6: int32, CallFunc_Not_PreBool_ReturnValue_5: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_22: bool, CallFunc_GetActorForwardVector_ReturnValue: FVector, CallFunc_K2_GetActorLocation_ReturnValue_4: FVector, CallFunc_SelectFloat_ReturnValue: float, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Normal_ReturnValue: FVector, CallFunc_Dot_VectorVector_ReturnValue: float, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_Multiply_FloatFloat_ReturnValue_8: float, CallFunc_EqualEqual_ByteByte_ReturnValue_23: bool, CallFunc_BooleanAND_ReturnValue_13: bool, CallFunc_BooleanAND_ReturnValue_14: bool, CallFunc_GetGameMode_ReturnValue: AGameModeBase*, CallFunc_SelectFloat_ReturnValue_1: float, K2Node_DynamicCast_AsHeist_GM: AHeistGM_C*, K2Node_DynamicCast_bSuccess_23: bool, CallFunc_GetGameMode_ReturnValue_1: AGameModeBase*, CallFunc_K2_GetActorLocation_ReturnValue_5: FVector, K2Node_DynamicCast_AsHeist_GM_1: AHeistGM_C*, K2Node_DynamicCast_bSuccess_24: bool, CallFunc_K2_GetRandomReachablePointInRadius_RandomLocation: FVector, CallFunc_K2_GetRandomReachablePointInRadius_ReturnValue: bool, CallFunc_Add_VectorVector_ReturnValue: FVector, CallFunc_K2_GetActorLocation_ReturnValue_6: FVector, CallFunc_MakeTransform_ReturnValue_1: FTransform, CallFunc_K2_GetRandomReachablePointInRadius_RandomLocation_1: FVector, CallFunc_K2_GetRandomReachablePointInRadius_ReturnValue_1: bool, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue_1: AActor*, CallFunc_Add_VectorVector_ReturnValue_1: FVector, CallFunc_FinishSpawningActor_ReturnValue_1: APlayerAI_Cop_C*, CallFunc_MakeTransform_ReturnValue_2: FTransform, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue_2: AActor*, CallFunc_EqualEqual_ByteByte_ReturnValue_24: bool, CallFunc_FinishSpawningActor_ReturnValue_2: APlayerAI_Cop_C*, CallFunc_IsValid_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_25: bool, CallFunc_GetDistanceTo_ReturnValue: float, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_26: bool, CallFunc_BooleanAND_ReturnValue_15: bool, CallFunc_Not_PreBool_ReturnValue_6: bool, CallFunc_SelectFloat_ReturnValue_2: float, CallFunc_SelectRotator_ReturnValue: FRotator, CallFunc_getCurrentMaskInfo_fasterInteract: bool, CallFunc_getCurrentMaskInfo_hpReg: bool, CallFunc_getCurrentMaskInfo_fasterSprintMoney: bool, CallFunc_getCurrentMaskInfo_reduceHpTick: bool, CallFunc_getCurrentMaskInfo_interestMoneybag: bool, CallFunc_getCurrentMaskInfo_reduceFallDmg: bool, CallFunc_getCurrentMaskInfo_reduceExplDmg: bool, CallFunc_getCurrentMaskInfo_fasterBags: bool, CallFunc_getCurrentMaskInfo_newbomb: bool, CallFunc_getCurrentMaskInfo_canttakeoff: bool, CallFunc_getCurrentMaskInfo_cdr: float, CallFunc_getCurrentMaskInfo_doubleJump_: bool, CallFunc_getCurrentMaskInfo_invisForCCTV_: bool, CallFunc_getCurrentMaskInfo_gainAmmo_: bool, CallFunc_getCurrentMaskInfo_canRide_: bool, CallFunc_getCurrentMaskInfo_slowFall_: bool, CallFunc_getCurrentMaskInfo_FoodOnMoneyPickup_: bool, CallFunc_getCurrentMaskInfo_fasterBodyCarry: bool, CallFunc_getCurrentMaskInfo_spawnMoney_: bool, CallFunc_getCurrentMaskInfo_noPoisonDmg_: bool, CallFunc_getCurrentMaskInfo_chargeJump: bool, CallFunc_BooleanAND_ReturnValue_16: bool, CallFunc_SelectFloat_ReturnValue_3: float, CallFunc_GetGameMode_ReturnValue_2: AGameModeBase*, CallFunc_GetGameMode_ReturnValue_3: AGameModeBase*, K2Node_DynamicCast_AsHeist_GM_2: AHeistGM_C*, K2Node_DynamicCast_bSuccess_25: bool, K2Node_DynamicCast_AsHeist_GM_3: AHeistGM_C*, K2Node_DynamicCast_bSuccess_26: bool, Temp_int_Variable_7: int32, K2Node_DynamicCast_AsPlayer_Char_12: APlayerChar_C*, K2Node_DynamicCast_bSuccess_27: bool, CallFunc_Map_Find_Value: int32, CallFunc_Map_Find_ReturnValue: bool, CallFunc_Map_Find_Value_1: float, CallFunc_Map_Find_ReturnValue_1: bool, K2Node_DynamicCast_AsPlayer_Char_13: APlayerChar_C*, K2Node_DynamicCast_bSuccess_28: bool, CallFunc_Map_Find_Value_2: int32, CallFunc_Map_Find_ReturnValue_2: bool, CallFunc_Map_Find_Value_3: float, CallFunc_Map_Find_ReturnValue_3: bool, CallFunc_NotEqual_ByteByte_ReturnValue_4: bool, K2Node_DynamicCast_AsPlayer_Char_14: APlayerChar_C*, K2Node_DynamicCast_bSuccess_29: bool, CallFunc_Map_Find_Value_4: int32, CallFunc_Map_Find_ReturnValue_4: bool, CallFunc_Map_Find_Value_5: float, CallFunc_Map_Find_ReturnValue_5: bool, K2Node_DynamicCast_AsPlayer_Char_15: APlayerChar_C*, K2Node_DynamicCast_bSuccess_30: bool, CallFunc_Map_Find_Value_6: int32, CallFunc_Map_Find_ReturnValue_6: bool, CallFunc_Map_Find_Value_7: float, CallFunc_Map_Find_ReturnValue_7: bool, CallFunc_GetOwner_ReturnValue_2: AActor*, K2Node_DynamicCast_AsPlayer_Char_16: APlayerChar_C*, K2Node_DynamicCast_bSuccess_31: bool, K2Node_DynamicCast_AsPlayer_Char_17: APlayerChar_C*, K2Node_DynamicCast_bSuccess_32: bool, CallFunc_K2_GetActorLocation_ReturnValue_7: FVector, CallFunc_GetGameState_ReturnValue: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess_33: bool, CallFunc_GetGameState_ReturnValue_1: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS_1: AHeistGS_C*, K2Node_DynamicCast_bSuccess_34: bool, CallFunc_Subtract_IntInt_ReturnValue_3: int32, CallFunc_Greater_IntInt_ReturnValue_2: bool, CallFunc_BooleanOR_ReturnValue_3: bool, CallFunc_GetGameMode_ReturnValue_4: AGameModeBase*, CallFunc_GetGameInstance_ReturnValue: UGameInstance*, K2Node_DynamicCast_AsHeist_GM_4: AHeistGM_C*, K2Node_DynamicCast_bSuccess_35: bool, K2Node_DynamicCast_AsHeist_GI: UHeistGI_C*, K2Node_DynamicCast_bSuccess_36: bool, CallFunc_BooleanAND_ReturnValue_17: bool, CallFunc_BooleanAND_ReturnValue_18: bool, CallFunc_Add_IntInt_ReturnValue_5: int32, CallFunc_BooleanAND_ReturnValue_19: bool, CallFunc_getAlivePlayersFromTeams_CopsAlive: TArray, CallFunc_getAlivePlayersFromTeams_CopsNum: int32, CallFunc_getAlivePlayersFromTeams_RobsAlive: TArray, CallFunc_getAlivePlayersFromTeams_RobsNum: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_Multiply_FloatFloat_ReturnValue_9: float, CallFunc_Multiply_FloatFloat_ReturnValue_10: float, CallFunc_SelectFloat_ReturnValue_4: float, CallFunc_GetGameMode_ReturnValue_5: AGameModeBase*, CallFunc_getAlivePlayersFromTeams_CopsAlive_1: TArray, CallFunc_getAlivePlayersFromTeams_CopsNum_1: int32, CallFunc_getAlivePlayersFromTeams_RobsAlive_1: TArray, CallFunc_getAlivePlayersFromTeams_RobsNum_1: int32, K2Node_DynamicCast_AsHeist_GM_5: AHeistGM_C*, K2Node_DynamicCast_bSuccess_37: bool, CallFunc_LessEqual_IntInt_ReturnValue_1: bool, CallFunc_GetGameState_ReturnValue_2: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS_2: AHeistGS_C*, K2Node_DynamicCast_bSuccess_38: bool, CallFunc_NotEqual_BoolBool_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue_4: int32, CallFunc_Greater_IntInt_ReturnValue_3: bool, Temp_int_Variable_8: int32, CallFunc_Divide_FloatFloat_ReturnValue_3: float, CallFunc_Not_PreBool_ReturnValue_7: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_27: bool, CallFunc_BooleanAND_ReturnValue_20: bool, CallFunc_K2_GetActorLocation_ReturnValue_8: FVector, CallFunc_BooleanAND_ReturnValue_21: bool, CallFunc_FindLookAtRotation_ReturnValue_2: FRotator, CallFunc_BreakRotator_Roll_1: float, CallFunc_BreakRotator_Pitch_1: float, CallFunc_BreakRotator_Yaw_1: float, CallFunc_MakeRotator_ReturnValue_2: FRotator, CallFunc_GreaterEqual_FloatFloat_ReturnValue_1: bool, CallFunc_EqualEqual_RotatorRotator_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_22: bool, CallFunc_BooleanAND_ReturnValue_23: bool, CallFunc_BooleanAND_ReturnValue_24: bool, CallFunc_SelectFloat_ReturnValue_5: float, CallFunc_BooleanAND_ReturnValue_25: bool, CallFunc_SelectFloat_ReturnValue_6: float, CallFunc_getCurrentMaskInfo_fasterInteract_1: bool, CallFunc_getCurrentMaskInfo_hpReg_1: bool, CallFunc_getCurrentMaskInfo_fasterSprintMoney_1: bool, CallFunc_getCurrentMaskInfo_reduceHpTick_1: bool, CallFunc_getCurrentMaskInfo_interestMoneybag_1: bool, CallFunc_getCurrentMaskInfo_reduceFallDmg_1: bool, CallFunc_getCurrentMaskInfo_reduceExplDmg_1: bool, CallFunc_getCurrentMaskInfo_fasterBags_1: bool, CallFunc_getCurrentMaskInfo_newbomb_1: bool, CallFunc_getCurrentMaskInfo_canttakeoff_1: bool, CallFunc_getCurrentMaskInfo_cdr_1: float, CallFunc_getCurrentMaskInfo_doubleJump__1: bool, CallFunc_getCurrentMaskInfo_invisForCCTV__1: bool, CallFunc_getCurrentMaskInfo_gainAmmo__1: bool, CallFunc_getCurrentMaskInfo_canRide__1: bool, CallFunc_getCurrentMaskInfo_slowFall__1: bool, CallFunc_getCurrentMaskInfo_FoodOnMoneyPickup__1: bool, CallFunc_getCurrentMaskInfo_fasterBodyCarry_1: bool, CallFunc_getCurrentMaskInfo_spawnMoney__1: bool, CallFunc_getCurrentMaskInfo_noPoisonDmg__1: bool, CallFunc_getCurrentMaskInfo_chargeJump_1: bool, CallFunc_BooleanAND_ReturnValue_26: bool, CallFunc_BooleanAND_ReturnValue_27: bool, CallFunc_BooleanAND_ReturnValue_28: bool, CallFunc_BooleanAND_ReturnValue_29: bool, CallFunc_SelectFloat_ReturnValue_7: float, CallFunc_SelectFloat_ReturnValue_8: float, CallFunc_EqualEqual_ByteByte_ReturnValue_28: bool, CallFunc_BooleanAND_ReturnValue_30: bool, CallFunc_BooleanAND_ReturnValue_31: bool, CallFunc_BooleanAND_ReturnValue_32: bool, CallFunc_SelectFloat_ReturnValue_9: float, CallFunc_EqualEqual_ByteByte_ReturnValue_29: bool, CallFunc_Not_PreBool_ReturnValue_8: bool, CallFunc_BooleanAND_ReturnValue_33: bool, CallFunc_SelectFloat_ReturnValue_10: float, CallFunc_EqualEqual_ByteByte_ReturnValue_30: bool, CallFunc_Not_PreBool_ReturnValue_9: bool, CallFunc_BooleanAND_ReturnValue_34: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_31: bool, CallFunc_Not_PreBool_ReturnValue_10: bool, CallFunc_BooleanAND_ReturnValue_35: bool, CallFunc_IsValid_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_36: bool, CallFunc_SelectFloat_ReturnValue_11: float, CallFunc_GetController_ReturnValue_4: AController*, K2Node_DynamicCast_AsHeist_PC_4: AHeistPC_C*, K2Node_DynamicCast_bSuccess_39: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_GetGameState_ReturnValue_3: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS_3: AHeistGS_C*, K2Node_DynamicCast_bSuccess_40: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_32: bool, CallFunc_Add_IntInt_ReturnValue_6: int32, CallFunc_Greater_FloatFloat_ReturnValue_1: bool, CallFunc_Greater_FloatFloat_ReturnValue_2: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_33: bool, CallFunc_BooleanAND_ReturnValue_37: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float, CallFunc_BooleanAND_ReturnValue_38: bool, CallFunc_FMax_ReturnValue: float, CallFunc_GreaterEqual_FloatFloat_ReturnValue_2: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_34: bool, CallFunc_BooleanAND_ReturnValue_39: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_35: bool, CallFunc_BooleanAND_ReturnValue_40: bool, CallFunc_SelectFloat_ReturnValue_12: float, CallFunc_BooleanAND_ReturnValue_41: bool, CallFunc_SelectFloat_ReturnValue_13: float, CallFunc_BooleanAND_ReturnValue_42: bool, CallFunc_BooleanOR_ReturnValue_4: bool, CallFunc_BooleanAND_ReturnValue_43: bool, CallFunc_BooleanAND_ReturnValue_44: bool, CallFunc_BooleanAND_ReturnValue_45: bool, CallFunc_SelectFloat_ReturnValue_14: float, CallFunc_Subtract_FloatFloat_ReturnValue_1: float, CallFunc_Greater_FloatFloat_ReturnValue_3: bool, CallFunc_UtcNow_ReturnValue: FDateTime, K2Node_MakeStruct_DeathInfo: FDeathInfo__pf1458230002, K2Node_MakeStruct_DeathInfo_1: FDeathInfo__pf1458230002, CallFunc_UtcNow_ReturnValue_1: FDateTime, K2Node_MakeStruct_DeathInfo_2: FDeathInfo__pf1458230002, CallFunc_GetGameMode_ReturnValue_6: AGameModeBase*, CallFunc_getAlivePlayersFromTeams_CopsAlive_2: TArray, CallFunc_getAlivePlayersFromTeams_CopsNum_2: int32, CallFunc_getAlivePlayersFromTeams_RobsAlive_2: TArray, CallFunc_getAlivePlayersFromTeams_RobsNum_2: int32, K2Node_DynamicCast_AsHeist_GM_6: AHeistGM_C*, K2Node_DynamicCast_bSuccess_41: bool, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_LessEqual_IntInt_ReturnValue_2: bool, CallFunc_GetGameState_ReturnValue_4: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS_4: AHeistGS_C*, K2Node_DynamicCast_bSuccess_42: bool, CallFunc_Subtract_IntInt_ReturnValue_5: int32, CallFunc_Greater_IntInt_ReturnValue_4: bool, CallFunc_BooleanOR_ReturnValue_5: bool, Temp_int_Variable_9: int32, CallFunc_Subtract_FloatFloat_ReturnValue_2: float, CallFunc_FClamp_ReturnValue: float, CallFunc_Not_PreBool_ReturnValue_11: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_36: bool, CallFunc_BooleanAND_ReturnValue_46: bool, CallFunc_Not_PreBool_ReturnValue_12: bool, CallFunc_SelectFloat_ReturnValue_15: float, CallFunc_EqualEqual_ByteByte_ReturnValue_37: bool, CallFunc_BooleanAND_ReturnValue_47: bool, CallFunc_Not_PreBool_ReturnValue_13: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_38: bool, CallFunc_BooleanAND_ReturnValue_48: bool, CallFunc_Not_PreBool_ReturnValue_14: bool, CallFunc_Subtract_FloatFloat_ReturnValue_3: float, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_LessEqual_FloatFloat_ReturnValue_1: bool, CallFunc_Conv_VectorToString_ReturnValue_1: FString, CallFunc_BooleanAND_ReturnValue_49: bool, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_SelectFloat_ReturnValue_16: float, CallFunc_VSize_ReturnValue: float, CallFunc_Conv_FloatToString_ReturnValue_1: FString, CallFunc_LessEqual_FloatFloat_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_50: bool, CallFunc_Conv_BoolToString_ReturnValue_1: FString, CallFunc_BooleanAND_ReturnValue_51: bool, CallFunc_Concat_StrStr_ReturnValue_5: FString, CallFunc_SelectFloat_ReturnValue_17: float, CallFunc_Concat_StrStr_ReturnValue_6: FString, CallFunc_Concat_StrStr_ReturnValue_7: FString, CallFunc_Not_PreBool_ReturnValue_15: bool, CallFunc_Concat_StrStr_ReturnValue_8: FString, CallFunc_BooleanAND_ReturnValue_52: bool, CallFunc_Concat_StrStr_ReturnValue_9: FString, CallFunc_SelectFloat_ReturnValue_18: float, CallFunc_Concat_StrStr_ReturnValue_10: FString, CallFunc_Concat_StrStr_ReturnValue_11: FString, CallFunc_Concat_StrStr_ReturnValue_12: FString, CallFunc_Concat_StrStr_ReturnValue_13: FString | void |
| GetLocalVar | Key: FString, Value: FString, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, CallFunc_Array_Get_Item: FF_SavedVar__pf523916617, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_EqualEqual_StrStr_ReturnValue: bool | void |
| SetLocalVar | Key: FString, Value: FString, K2Node_MakeStruct_F_SavedVar: FF_SavedVar__pf523916617, K2Node_MakeStruct_F_SavedVar_1: FF_SavedVar__pf523916617, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, CallFunc_Array_Get_Item: FF_SavedVar__pf523916617, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_EqualEqual_StrStr_ReturnValue: bool, CallFunc_Array_Add_ReturnValue: int32 | void |
| GetReplicatedVar | Key: FString, Value: FString, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: FF_SavedVar__pf523916617, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_EqualEqual_StrStr_ReturnValue: bool | void |
| SetReplicatedVar | Key: FString, Value: FString, K2Node_MakeStruct_F_SavedVar: FF_SavedVar__pf523916617, K2Node_MakeStruct_F_SavedVar_1: FF_SavedVar__pf523916617, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, CallFunc_Array_Add_ReturnValue: int32, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: FF_SavedVar__pf523916617, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_EqualEqual_StrStr_ReturnValue: bool | void |
| handleOnRepClass | Temp_bool_Variable: bool, Temp_object_Variable: UStaticMesh*, CallFunc_SelectFloat_ReturnValue: float, CallFunc_IsLocallyControlled_ReturnValue: bool, CallFunc_GetMyMovementComponent_ReturnValue: UMyCharacterMovementComponent*, CallFunc_GetClassSprintSpeed_Speed: float, CallFunc_FindClassRow_row: FClassesStruct__pf1489439355, CallFunc_FindClassRow_rowName: FName, CallFunc_K2_AttachToComponent_ReturnValue: bool, K2Node_Select_Default: UStaticMesh*, CallFunc_SetStaticMesh_ReturnValue: bool | void |
| OnRep_CustomClassString | none | void |
| UpdateJumpVelocity | CallFunc_getCurrentMultiPurposeZone_noPunch: bool, CallFunc_getCurrentMultiPurposeZone_noActiveAbility: bool, CallFunc_getCurrentMultiPurposeZone_jumpModi: float, CallFunc_getCurrentMultiPurposeZone_sprintModi: float, CallFunc_getCurrentMultiPurposeZone_noFallDmg: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_SelectFloat_ReturnValue: float, CallFunc_Multiply_FloatFloat_ReturnValue: float | void |
| usingStamina | stamina?: bool, reason: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_GetGameState_ReturnValue: AGameStateBase*, CallFunc_BooleanAND_ReturnValue_1: bool, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess: bool | void |
| SetClass | classID: uint8 | void |
| SetRobber | robber: bool, r: int32, CallFunc_RandomIntegerInRange_ReturnValue: int32, CallFunc_RandomInteger_ReturnValue: int32, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_Add_IntInt_ReturnValue_1: int32, CallFunc_Percent_IntInt_ReturnValue: int32, CallFunc_EqualEqual_IntInt_ReturnValue: bool, CallFunc_EqualEqual_IntInt_ReturnValue_1: bool, CallFunc_SelectInt_ReturnValue: int32, CallFunc_SelectInt_ReturnValue_1: int32, CallFunc_Multiply_IntInt_ReturnValue: int32, CallFunc_Multiply_IntInt_ReturnValue_1: int32, CallFunc_Add_IntInt_ReturnValue_2: int32, CallFunc_Add_IntInt_ReturnValue_3: int32 | void |
| isRobber | robber: bool, CallFunc_Percent_IntInt_ReturnValue: int32, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_Divide_IntInt_ReturnValue: int32, CallFunc_Percent_IntInt_ReturnValue_1: int32, CallFunc_EqualEqual_IntInt_ReturnValue: bool | void |
| isClass | robber: bool, classID: uint8, is: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_EqualEqual_BoolBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| getCurrentMaskID | ID: int32, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Conv_StringToName_ReturnValue: FName, CallFunc_GetDataTableRowFromName_OutRow: FMaskStruct__pf1458230002, CallFunc_GetDataTableRowFromName_ReturnValue: bool | void |
| OnRep_spawnprotect? | none | void |
| OnRep_spectator? | none | void |
| updatePlayersVC | CallFunc_GetPlayerController_ReturnValue: APlayerController*, CallFunc_GetPlayerPawn_ReturnValue: APawn*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_shouldPlayerBeMutedVC_muted: bool, CallFunc_shouldPlayerBeMutedVC_soundAtt: USoundAttenuation*, CallFunc_shouldPlayerBeMutedVC_reason: FString, CallFunc_shouldPlayerBeMutedVC_mutePings: bool, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_Conv_BoolToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_IsValid_ReturnValue_1: bool, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_Concat_StrStr_ReturnValue_5: FString, CallFunc_Concat_StrStr_ReturnValue_6: FString, K2Node_MakeStruct_VoiceSettings: FVoiceSettings, CallFunc_Concat_StrStr_ReturnValue_7: FString, CallFunc_Concat_StrStr_ReturnValue_8: FString | void |
| shouldPlayerBeMutedVC | player: APlayerChar_C*, muted: bool, soundAtt: USoundAttenuation*, reason: FString, mutePings: bool, CallFunc_EqualEqual_BoolBool_ReturnValue: bool, CallFunc_EqualEqual_BoolBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_GetGameInstance_ReturnValue: UGameInstance*, K2Node_DynamicCast_AsHeist_GI: UHeistGI_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_GetGameState_ReturnValue: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_GetPlayerController_ReturnValue: APlayerController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess_2: bool, CallFunc_Array_Contains_ReturnValue: bool | void |
| updateAllVoiceChatMutes | Temp_int_Loop_Counter_Variable: int32, Temp_int_Array_Index_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: APlayerChar_C*, CallFunc_Less_IntInt_ReturnValue: bool | void |
| sameTeam? | other: APlayerChar_C*, same: bool, CallFunc_EqualEqual_BoolBool_ReturnValue: bool, CallFunc_EqualEqual_BoolBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| OnRep_talking? | CallFunc_Create_ReturnValue: UPlayerTalkingPart_C*, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_bool_True_if_break_was_hit_Variable: bool, CallFunc_Not_PreBool_ReturnValue: bool, Temp_int_Array_Index_Variable: int32, CallFunc_GetPlayerController_ReturnValue: APlayerController*, CallFunc_GetPlayerController_ReturnValue_1: APlayerController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool, K2Node_DynamicCast_AsHeist_PC_1: AHeistPC_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_EqualEqual_BoolBool_ReturnValue: bool, CallFunc_AddChild_ReturnValue: UPanelSlot*, CallFunc_EqualEqual_BoolBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_GetAllWidgetsOfClass_FoundWidgets: TArray, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: UPlayerTalkingPart_C*, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool | void |
| isClass? | rob?: bool, id: uint8, is?: bool, CallFunc_EqualEqual_BoolBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| getRandomCustomerDisguise | SkeletalMesh: USkeletalMesh*, Material: UMaterial*, CallFunc_RandomIntegerInRange_ReturnValue: int32, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Conv_StringToName_ReturnValue: FName, CallFunc_GetDataTableRowFromName_OutRow: FClothingStruct__pf1458230002, CallFunc_GetDataTableRowFromName_ReturnValue: bool | void |
| OnRep_vestHP | CallFunc_IsLocallyControlled_ReturnValue: bool, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| Handle Player Hidden | forceHidden?: bool, CallFunc_getCurrentMaskInfo_fasterInteract: bool, CallFunc_getCurrentMaskInfo_hpReg: bool, CallFunc_getCurrentMaskInfo_fasterSprintMoney: bool, CallFunc_getCurrentMaskInfo_reduceHpTick: bool, CallFunc_getCurrentMaskInfo_interestMoneybag: bool, CallFunc_getCurrentMaskInfo_reduceFallDmg: bool, CallFunc_getCurrentMaskInfo_reduceExplDmg: bool, CallFunc_getCurrentMaskInfo_fasterBags: bool, CallFunc_getCurrentMaskInfo_newbomb: bool, CallFunc_getCurrentMaskInfo_canttakeoff: bool, CallFunc_getCurrentMaskInfo_cdr: float, CallFunc_getCurrentMaskInfo_doubleJump_: bool, CallFunc_getCurrentMaskInfo_invisForCCTV_: bool, CallFunc_getCurrentMaskInfo_gainAmmo_: bool, CallFunc_getCurrentMaskInfo_canRide_: bool, CallFunc_getCurrentMaskInfo_slowFall_: bool, CallFunc_getCurrentMaskInfo_FoodOnMoneyPickup_: bool, CallFunc_getCurrentMaskInfo_fasterBodyCarry: bool, CallFunc_getCurrentMaskInfo_spawnMoney_: bool, CallFunc_getCurrentMaskInfo_noPoisonDmg_: bool, CallFunc_getCurrentMaskInfo_chargeJump: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_GetPlayerController_ReturnValue: APlayerController*, CallFunc_BooleanOR_ReturnValue_1: bool, CallFunc_GetViewTarget_ReturnValue: AActor*, CallFunc_BooleanOR_ReturnValue_2: bool, K2Node_DynamicCast_AsCCTV: ACCTV_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_NotEqual_BoolBool_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue_3: bool, CallFunc_BooleanOR_ReturnValue_4: bool, CallFunc_BooleanOR_ReturnValue_5: bool, CallFunc_NotEqual_BoolBool_ReturnValue_1: bool | void |
| damagedPlayer | dmgedPlayer: APlayerChar_C*, dmg: float, Temp_int_Variable: int32, CallFunc_FTrunc_ReturnValue: int32, CallFunc_isClass__is_: bool, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_Clamp_ReturnValue: int32, CallFunc_Map_Find_Value: float, CallFunc_Map_Find_ReturnValue: bool, CallFunc_Map_Find_Value_1: int32, CallFunc_Map_Find_ReturnValue_1: bool, CallFunc_Add_IntInt_ReturnValue_1: int32, CallFunc_Add_FloatFloat_ReturnValue: float | void |
| handleBackShieldVis | CallFunc_Not_PreBool_ReturnValue: bool, K2Node_DynamicCast_AsRiot_Shield_Col: ARiotShieldCol_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_IsLocallyControlled_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanAND_ReturnValue_4: bool, CallFunc_BooleanAND_ReturnValue_5: bool | void |
| OnRep_painted? | CallFunc_GetPlayerController_ReturnValue: APlayerController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_IsLocalController_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| getCurrentMaskInfo | ignoreMaskOn?: bool, fasterInteract: bool, hpReg: bool, fasterSprintMoney: bool, reduceHpTick: bool, interestMoneybag: bool, reduceFallDmg: bool, reduceExplDmg: bool, fasterBags: bool, newbomb: bool, canttakeoff: bool, cdr: float, doubleJump?: bool, invisForCCTV?: bool, gainAmmo?: bool, canRide?: bool, slowFall?: bool, FoodOnMoneyPickup?: bool, fasterBodyCarry: bool, spawnMoney?: bool, noPoisonDmg?: bool, chargeJump: bool, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Conv_StringToName_ReturnValue: FName, CallFunc_GetDataTableRowFromName_OutRow: FMaskStruct__pf1458230002, CallFunc_GetDataTableRowFromName_ReturnValue: bool, CallFunc_EqualEqual_IntInt_ReturnValue: bool, CallFunc_EqualEqual_IntInt_ReturnValue_1: bool, CallFunc_EqualEqual_IntInt_ReturnValue_2: bool, CallFunc_EqualEqual_IntInt_ReturnValue_3: bool, CallFunc_EqualEqual_IntInt_ReturnValue_4: bool, CallFunc_EqualEqual_IntInt_ReturnValue_5: bool, CallFunc_EqualEqual_IntInt_ReturnValue_6: bool, CallFunc_EqualEqual_IntInt_ReturnValue_7: bool, CallFunc_EqualEqual_IntInt_ReturnValue_8: bool, CallFunc_EqualEqual_IntInt_ReturnValue_9: bool, CallFunc_SelectFloat_ReturnValue: float, CallFunc_EqualEqual_IntInt_ReturnValue_10: bool, CallFunc_EqualEqual_IntInt_ReturnValue_11: bool, CallFunc_EqualEqual_IntInt_ReturnValue_12: bool, CallFunc_EqualEqual_IntInt_ReturnValue_13: bool, CallFunc_EqualEqual_IntInt_ReturnValue_14: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_EqualEqual_IntInt_ReturnValue_15: bool, CallFunc_EqualEqual_IntInt_ReturnValue_16: bool | void |
| OnRep_maskOn? | CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_getCurrentMaskInfo_fasterInteract: bool, CallFunc_getCurrentMaskInfo_hpReg: bool, CallFunc_getCurrentMaskInfo_fasterSprintMoney: bool, CallFunc_getCurrentMaskInfo_reduceHpTick: bool, CallFunc_getCurrentMaskInfo_interestMoneybag: bool, CallFunc_getCurrentMaskInfo_reduceFallDmg: bool, CallFunc_getCurrentMaskInfo_reduceExplDmg: bool, CallFunc_getCurrentMaskInfo_fasterBags: bool, CallFunc_getCurrentMaskInfo_newbomb: bool, CallFunc_getCurrentMaskInfo_canttakeoff: bool, CallFunc_getCurrentMaskInfo_cdr: float, CallFunc_getCurrentMaskInfo_doubleJump_: bool, CallFunc_getCurrentMaskInfo_invisForCCTV_: bool, CallFunc_getCurrentMaskInfo_gainAmmo_: bool, CallFunc_getCurrentMaskInfo_canRide_: bool, CallFunc_getCurrentMaskInfo_slowFall_: bool, CallFunc_getCurrentMaskInfo_FoodOnMoneyPickup_: bool, CallFunc_getCurrentMaskInfo_fasterBodyCarry: bool, CallFunc_getCurrentMaskInfo_spawnMoney_: bool, CallFunc_getCurrentMaskInfo_noPoisonDmg_: bool, CallFunc_getCurrentMaskInfo_chargeJump: bool, CallFunc_SelectFloat_ReturnValue: float, CallFunc_SelectFloat_ReturnValue_1: float, CallFunc_GetClassSprintSpeed_Speed: float, K2Node_DynamicCast_AsMy_Character_Movement_Component: UMyCharacterMovementComponent*, K2Node_DynamicCast_bSuccess: bool, CallFunc_IsLocallyControlled_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool | void |
| OnRep_selectedMask | CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Conv_StringToName_ReturnValue: FName, CallFunc_GetDataTableRowFromName_OutRow: FMaskStruct__pf1458230002, CallFunc_GetDataTableRowFromName_ReturnValue: bool, CallFunc_Conv_VectorToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_SetStaticMesh_ReturnValue: bool | void |
| OnRep_tasered? | none | void |
| OnRep_roped? | none | void |
| OnRep_hidden? | CallFunc_Conv_BoolToString_ReturnValue: FString, CallFunc_Conv_BoolToString_ReturnValue_1: FString, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_SelectFloat_ReturnValue: float, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Conv_BoolToString_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_Concat_StrStr_ReturnValue_5: FString | void |
| MaybeUpdateHudChar | CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_GetAllActorsOfClass_OutActors_1: TArray, CallFunc_Array_Get_Item: AHUD_Character_C*, CallFunc_Array_Get_Item_1: ASCC_HUD_C*, CallFunc_IsLocallyControlled_ReturnValue: bool, CallFunc_GetGameInstance_ReturnValue: UGameInstance*, K2Node_DynamicCast_AsHeist_GI: UHeistGI_C*, K2Node_DynamicCast_bSuccess: bool | void |
| CanJumpInternal | Temp_object_Variable: TArray, CallFunc_GetOverlappingActors_OverlappingActors: TArray, CallFunc_Array_Length_ReturnValue: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_getCurrentMaskInfo_fasterInteract: bool, CallFunc_getCurrentMaskInfo_hpReg: bool, CallFunc_getCurrentMaskInfo_fasterSprintMoney: bool, CallFunc_getCurrentMaskInfo_reduceHpTick: bool, CallFunc_getCurrentMaskInfo_interestMoneybag: bool, CallFunc_getCurrentMaskInfo_reduceFallDmg: bool, CallFunc_getCurrentMaskInfo_reduceExplDmg: bool, CallFunc_getCurrentMaskInfo_fasterBags: bool, CallFunc_getCurrentMaskInfo_newbomb: bool, CallFunc_getCurrentMaskInfo_canttakeoff: bool, CallFunc_getCurrentMaskInfo_cdr: float, CallFunc_getCurrentMaskInfo_doubleJump_: bool, CallFunc_getCurrentMaskInfo_invisForCCTV_: bool, CallFunc_getCurrentMaskInfo_gainAmmo_: bool, CallFunc_getCurrentMaskInfo_canRide_: bool, CallFunc_getCurrentMaskInfo_slowFall_: bool, CallFunc_getCurrentMaskInfo_FoodOnMoneyPickup_: bool, CallFunc_getCurrentMaskInfo_fasterBodyCarry: bool, CallFunc_getCurrentMaskInfo_spawnMoney_: bool, CallFunc_getCurrentMaskInfo_noPoisonDmg_: bool, CallFunc_getCurrentMaskInfo_chargeJump: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_GetActorForwardVector_ReturnValue: FVector, CallFunc_Multiply_VectorInt_ReturnValue: FVector, CallFunc_Add_VectorVector_ReturnValue: FVector, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_IsFalling_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_3: bool | bool |
| OnRep_DeathInfo | CallFunc_EqualEqual_DateTimeDateTime_ReturnValue: bool | void |
| HandleGotShotSV | CallFunc_IsValid_ReturnValue: bool, CallFunc_IsValid_ReturnValue_1: bool, CallFunc_GetController_ReturnValue: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_GetController_ReturnValue_1: AController*, K2Node_DynamicCast_AsHeist_PC_1: AHeistPC_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_IsValid_ReturnValue_2: bool, CallFunc_GetController_ReturnValue_2: AController*, K2Node_DynamicCast_AsHeist_PC_2: AHeistPC_C*, K2Node_DynamicCast_bSuccess_2: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue_1: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue_2: bool | void |
| HandleGotShot | DmgSource: AActor*, dontSlow: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_GetGameTimeSinceCreation_ReturnValue: float, CallFunc_GetPlayerPawn_ReturnValue: APawn*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, CallFunc_Create_ReturnValue: UHitIndicatorWidget_C*, CallFunc_IsValid_ReturnValue_1: bool | void |
| GetClassSprintSpeed | classID: uint8, rob?: bool, Speed: float, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_getCurrentMultiPurposeZone_noPunch: bool, CallFunc_getCurrentMultiPurposeZone_noActiveAbility: bool, CallFunc_getCurrentMultiPurposeZone_jumpModi: float, CallFunc_getCurrentMultiPurposeZone_sprintModi: float, CallFunc_getCurrentMultiPurposeZone_noFallDmg: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_TextIsEmpty_ReturnValue: bool, CallFunc_SelectFloat_ReturnValue: float, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_3: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_SelectFloat_ReturnValue_1: float, CallFunc_IsValid_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue_1: bool, CallFunc_Greater_IntInt_ReturnValue_1: bool, CallFunc_BooleanOR_ReturnValue_2: bool, CallFunc_BooleanOR_ReturnValue_3: bool, CallFunc_getCurrentMaskInfo_fasterInteract: bool, CallFunc_getCurrentMaskInfo_hpReg: bool, CallFunc_getCurrentMaskInfo_fasterSprintMoney: bool, CallFunc_getCurrentMaskInfo_reduceHpTick: bool, CallFunc_getCurrentMaskInfo_interestMoneybag: bool, CallFunc_getCurrentMaskInfo_reduceFallDmg: bool, CallFunc_getCurrentMaskInfo_reduceExplDmg: bool, CallFunc_getCurrentMaskInfo_fasterBags: bool, CallFunc_getCurrentMaskInfo_newbomb: bool, CallFunc_getCurrentMaskInfo_canttakeoff: bool, CallFunc_getCurrentMaskInfo_cdr: float, CallFunc_getCurrentMaskInfo_doubleJump_: bool, CallFunc_getCurrentMaskInfo_invisForCCTV_: bool, CallFunc_getCurrentMaskInfo_gainAmmo_: bool, CallFunc_getCurrentMaskInfo_canRide_: bool, CallFunc_getCurrentMaskInfo_slowFall_: bool, CallFunc_getCurrentMaskInfo_FoodOnMoneyPickup_: bool, CallFunc_getCurrentMaskInfo_fasterBodyCarry: bool, CallFunc_getCurrentMaskInfo_spawnMoney_: bool, CallFunc_getCurrentMaskInfo_noPoisonDmg_: bool, CallFunc_getCurrentMaskInfo_chargeJump: bool, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanAND_ReturnValue_4: bool, CallFunc_BooleanAND_ReturnValue_5: bool, CallFunc_SelectFloat_ReturnValue_2: float, CallFunc_SelectFloat_ReturnValue_3: float, CallFunc_SelectFloat_ReturnValue_4: float, CallFunc_SelectFloat_ReturnValue_5: float, CallFunc_Multiply_FloatFloat_ReturnValue: float | void |
| getAllValidSpectatingTargets | possibleSpecTargets: TArray, possibleTargets: TArray, Temp_int_Array_Index_Variable: int32, Temp_int_Array_Index_Variable_1: int32, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable_2: int32, Temp_int_Loop_Counter_Variable_1: int32, CallFunc_Add_IntInt_ReturnValue_1: int32, Temp_int_Loop_Counter_Variable_2: int32, Temp_int_Loop_Counter_Variable_3: int32, CallFunc_Add_IntInt_ReturnValue_2: int32, CallFunc_Add_IntInt_ReturnValue_3: int32, Temp_int_Array_Index_Variable_3: int32, Temp_int_Array_Index_Variable_4: int32, Temp_int_Loop_Counter_Variable_4: int32, CallFunc_Add_IntInt_ReturnValue_4: int32, Temp_int_Array_Index_Variable_5: int32, Temp_int_Loop_Counter_Variable_5: int32, CallFunc_Add_IntInt_ReturnValue_5: int32, Temp_int_Loop_Counter_Variable_6: int32, CallFunc_Add_IntInt_ReturnValue_6: int32, Temp_int_Array_Index_Variable_6: int32, Temp_int_Loop_Counter_Variable_7: int32, CallFunc_Add_IntInt_ReturnValue_7: int32, Temp_int_Array_Index_Variable_7: int32, Temp_int_Loop_Counter_Variable_8: int32, CallFunc_Add_IntInt_ReturnValue_8: int32, Temp_bool_True_if_break_was_hit_Variable: bool, CallFunc_Not_PreBool_ReturnValue: bool, Temp_int_Array_Index_Variable_8: int32, Temp_int_Loop_Counter_Variable_9: int32, CallFunc_Add_IntInt_ReturnValue_9: int32, Temp_bool_True_if_break_was_hit_Variable_1: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, Temp_int_Array_Index_Variable_9: int32, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_Not_PreBool_ReturnValue_3: bool, CallFunc_Not_PreBool_ReturnValue_4: bool, CallFunc_Not_PreBool_ReturnValue_5: bool, CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_Array_Get_Item: AHorseChar_C*, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_Array_Add_ReturnValue: int32, CallFunc_GetAllActorsOfClass_OutActors_1: TArray, CallFunc_Array_Get_Item_1: APaperPlane_C*, CallFunc_Array_Length_ReturnValue_1: int32, CallFunc_Array_Add_ReturnValue_1: int32, CallFunc_Less_IntInt_ReturnValue_1: bool, CallFunc_GetAllActorsOfClass_OutActors_2: TArray, CallFunc_Array_Get_Item_2: APlayerAI_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_6: bool, CallFunc_Array_Add_ReturnValue_2: int32, CallFunc_Array_Length_ReturnValue_2: int32, CallFunc_Not_PreBool_ReturnValue_7: bool, CallFunc_Less_IntInt_ReturnValue_2: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_EqualEqual_BoolBool_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_GetAllActorsOfClass_OutActors_3: TArray, CallFunc_Array_Get_Item_3: ACCTV_C*, CallFunc_Array_Length_ReturnValue_3: int32, CallFunc_Array_Add_ReturnValue_3: int32, CallFunc_Less_IntInt_ReturnValue_3: bool, CallFunc_GetAllActorsOfClass_OutActors_4: TArray, CallFunc_Array_Get_Item_4: AHorseChar_C*, CallFunc_Array_Length_ReturnValue_4: int32, CallFunc_Less_IntInt_ReturnValue_4: bool, CallFunc_Array_Add_ReturnValue_4: int32, CallFunc_GetAllActorsOfClass_OutActors_5: TArray, CallFunc_Array_Get_Item_5: ACCTV_C*, CallFunc_Array_Length_ReturnValue_5: int32, CallFunc_Array_Add_ReturnValue_5: int32, CallFunc_Less_IntInt_ReturnValue_5: bool, CallFunc_GetAllActorsOfClass_OutActors_6: TArray, CallFunc_Array_Get_Item_6: ABombBuggy_C*, CallFunc_Array_Length_ReturnValue_6: int32, CallFunc_Array_Add_ReturnValue_6: int32, CallFunc_Less_IntInt_ReturnValue_6: bool, CallFunc_GetAllActorsOfClass_OutActors_7: TArray, CallFunc_Array_Get_Item_7: ATechDrone_C*, CallFunc_Array_Add_ReturnValue_7: int32, CallFunc_Array_Length_ReturnValue_7: int32, CallFunc_Less_IntInt_ReturnValue_7: bool, CallFunc_Array_Length_ReturnValue_8: int32, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_GetAllActorsOfClass_OutActors_8: TArray, CallFunc_Array_Length_ReturnValue_9: int32, CallFunc_Array_Get_Item_8: APlayerChar_C*, CallFunc_Less_IntInt_ReturnValue_8: bool, CallFunc_Array_Add_ReturnValue_8: int32, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_EqualEqual_BoolBool_ReturnValue_1: bool, CallFunc_Array_Get_Item_9: APlayerChar_C*, CallFunc_Array_Add_ReturnValue_9: int32, CallFunc_Not_PreBool_ReturnValue_8: bool, CallFunc_NotEqual_ObjectObject_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_9: bool, CallFunc_Not_PreBool_ReturnValue_10: bool, CallFunc_EqualEqual_BoolBool_ReturnValue_2: bool, CallFunc_BooleanOR_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_4: bool, CallFunc_BooleanAND_ReturnValue_5: bool, CallFunc_Array_Length_ReturnValue_10: int32, CallFunc_BooleanOR_ReturnValue_3: bool, CallFunc_Less_IntInt_ReturnValue_9: bool, CallFunc_BooleanAND_ReturnValue_6: bool, CallFunc_BooleanAND_ReturnValue_7: bool, CallFunc_BooleanAND_ReturnValue_8: bool, CallFunc_BooleanAND_ReturnValue_9: bool | void |
| isDisguised? | disguised?: bool, movement?: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_GetInputAxisValue_ReturnValue: float, CallFunc_Abs_ReturnValue: float, CallFunc_GetInputAxisValue_ReturnValue_1: float, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_GetOverlappingActors_OverlappingActors: TArray, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_NotEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_SelectInt_ReturnValue: int32, CallFunc_Greater_IntInt_ReturnValue_1: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_VSize_ReturnValue: float, CallFunc_Less_FloatFloat_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_NotEqual_ObjectObject_ReturnValue: bool, CallFunc_NotEqual_ByteByte_ReturnValue_1: bool, CallFunc_IsCrouching_ReturnValue: bool, CallFunc_VSize_ReturnValue_1: float, CallFunc_Greater_FloatFloat_ReturnValue_1: bool, CallFunc_IsFalling_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool | FText |
| getAlivePlayersFromTeams | countBots?: bool, CopsAlive: TArray, CopsNum: int32, RobsAlive: TArray, RobsNum: int32, aiCops: TArray, aiRobs: TArray, aliverobs: TArray, alivecops: TArray, Temp_int_Array_Index_Variable: int32, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Loop_Counter_Variable_1: int32, CallFunc_Add_IntInt_ReturnValue_1: int32, Temp_int_Array_Index_Variable_1: int32, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Length_ReturnValue_1: int32, CallFunc_Array_Length_ReturnValue_2: int32, CallFunc_Array_Length_ReturnValue_3: int32, CallFunc_Add_IntInt_ReturnValue_2: int32, CallFunc_Add_IntInt_ReturnValue_3: int32, CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_Array_Get_Item: APlayerAI_C*, CallFunc_Array_Length_ReturnValue_4: int32, CallFunc_Array_Add_ReturnValue: int32, CallFunc_Array_Add_ReturnValue_1: int32, CallFunc_Array_Length_ReturnValue_5: int32, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_Array_Length_ReturnValue_6: int32, CallFunc_GetAllActorsOfClass_OutActors_1: TArray, CallFunc_Array_Length_ReturnValue_7: int32, CallFunc_Array_Get_Item_1: APlayerChar_C*, CallFunc_Less_IntInt_ReturnValue_1: bool, CallFunc_Conv_BoolToString_ReturnValue: FString, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_K2_IsValidTimerHandle_ReturnValue: bool, CallFunc_Array_AddUnique_ReturnValue: int32, CallFunc_Conv_BoolToString_ReturnValue_1: FString, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_Array_AddUnique_ReturnValue_1: int32, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Conv_BoolToString_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_BooleanOR_ReturnValue_1: bool, CallFunc_Concat_StrStr_ReturnValue_5: FString, CallFunc_Concat_StrStr_ReturnValue_6: FString | void |
| OnRep_dead? | CallFunc_Conv_BoolToString_ReturnValue: FString, CallFunc_Conv_BoolToString_ReturnValue_1: FString, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_SelectFloat_ReturnValue: float, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Conv_BoolToString_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_3: FString | void |
| HealPlayer | amount: float, CallFunc_HasAuthority_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FMax_ReturnValue: float, CallFunc_FMin_ReturnValue: float | void |
| FindClassRow | robber?: bool, ClassID: uint8, customClass: FString, row: FClassesStruct__pf1489439355, rowName: FName, foundName: FName, found: bool, foundRow: FClassesStruct__pf1489439355, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_bool_True_if_break_was_hit_Variable: bool, CallFunc_Not_PreBool_ReturnValue: bool, Temp_int_Array_Index_Variable: int32, Temp_int_Loop_Counter_Variable_1: int32, CallFunc_Add_IntInt_ReturnValue_1: int32, Temp_bool_True_if_break_was_hit_Variable_1: bool, Temp_int_Array_Index_Variable_1: int32, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_Conv_StringToName_ReturnValue: FName, CallFunc_getHeistGS_gs: AHeistGS_C*, CallFunc_Map_Find_Value: FClassesStruct__pf1489439355, CallFunc_Map_Find_ReturnValue: bool, CallFunc_GetDataTableRowNames_OutRowNames: TArray, CallFunc_Array_Get_Item: FName, CallFunc_GetDataTableRowFromName_OutRow: FClassesStruct__pf1489439355, CallFunc_GetDataTableRowFromName_ReturnValue: bool, CallFunc_Array_Length_ReturnValue: int32, CallFunc_EqualEqual_BoolBool_ReturnValue: bool, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_GetDataTableRowNames_OutRowNames_1: TArray, CallFunc_Array_Length_ReturnValue_1: int32, CallFunc_Array_Get_Item_1: FName, CallFunc_Less_IntInt_ReturnValue_1: bool, CallFunc_GetDataTableRowFromName_OutRow_1: FClassesStruct__pf1489439355, CallFunc_GetDataTableRowFromName_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_EqualEqual_BoolBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool | void |
| OnRep_robber? | CallFunc_FindClassRow_row: FClassesStruct__pf1489439355, CallFunc_FindClassRow_rowName: FName, CallFunc_IsValid_ReturnValue: bool, CallFunc_IsValid_ReturnValue_1: bool, CallFunc_IsLocallyControlled_ReturnValue: bool, CallFunc_GetPlayerCharacter_ReturnValue: ACharacter*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_IsValid_ReturnValue_2: bool | void |
| OnRep_hasTeam? | CallFunc_GetPlayerCharacter_ReturnValue: ACharacter*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_IsValid_ReturnValue: bool | void |
| OnRep_ClassID | none | void |
| CanJoinTeam | wantsRob?: bool, ignoreAlreadyInTeam?: bool, canJoin?: bool, CallFunc_GetSmallerTeamID_SmallerTeamIsRob_: bool, CallFunc_GetSmallerTeamID_equalCurrently_: bool, CallFunc_GetSmallerTeamID_TeamRobSize: int32, CallFunc_GetSmallerTeamID_TeamCopSize: int32, CallFunc_GetSmallerTeamID_PlayerCount: int32, CallFunc_IsPackagedForDistribution_ReturnValue: bool, CallFunc_EqualEqual_IntInt_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_Conv_IntToFloat_ReturnValue: float, CallFunc_Subtract_IntInt_ReturnValue_1: int32, CallFunc_Conv_IntToFloat_ReturnValue_1: float, CallFunc_Conv_IntToFloat_ReturnValue_2: float, CallFunc_Divide_FloatFloat_ReturnValue: float, CallFunc_Divide_FloatFloat_ReturnValue_1: float, CallFunc_Multiply_FloatFloat_ReturnValue: float, CallFunc_Multiply_FloatFloat_ReturnValue_1: float, CallFunc_GetGameInstance_ReturnValue: UGameInstance*, K2Node_DynamicCast_AsHeist_GI: UHeistGI_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_EqualEqual_BoolBool_ReturnValue: bool, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_GetGameState_ReturnValue: AGameStateBase*, CallFunc_GetObjectClass_ReturnValue: UClass*, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_GetClassDisplayName_ReturnValue: FString, CallFunc_GreaterEqual_FloatFloat_ReturnValue: bool, CallFunc_GreaterEqual_FloatFloat_ReturnValue_1: bool | void |
| GetSmallerTeamID | SmallerTeamIsRob?: bool, equalCurrently?: bool, TeamRobSize: int32, TeamCopSize: int32, PlayerCount: int32, Team2N: int32, Team1N: int32, Temp_int_Variable: int32, Temp_int_Variable_1: int32, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, CallFunc_Add_IntInt_ReturnValue_1: int32, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue_2: int32, CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: APlayerChar_C*, CallFunc_Array_Length_ReturnValue_1: int32, CallFunc_Less_IntInt_ReturnValue_1: bool | void |
| Set Clothes | CallFunc_CreateDynamicMaterialInstance_ReturnValue: UMaterialInstanceDynamic*, CallFunc_IsLocallyControlled_ReturnValue: bool, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_GetDisplayName_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_GetMaterial_ReturnValue: UMaterialInterface*, K2Node_DynamicCast_AsMaterial_Instance_Dynamic: UMaterialInstanceDynamic*, K2Node_DynamicCast_bSuccess: bool, CallFunc_GetGameState_ReturnValue: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_GetPlayerCharacter_ReturnValue: ACharacter*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess_2: bool, CallFunc_findPrimaryColorOfOutfit_color: FLinearColor | void |
| OnRep_MeshMatSv | none | void |
| OnRep_MeshSv | Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_bool_True_if_break_was_hit_Variable: bool, Temp_int_Array_Index_Variable: int32, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_GetDataTableRowNames_OutRowNames: TArray, CallFunc_Array_Get_Item: FName, CallFunc_Array_Length_ReturnValue: int32, CallFunc_GetDataTableRowFromName_OutRow: FClothingStruct__pf1458230002, CallFunc_GetDataTableRowFromName_ReturnValue: bool, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool | void |
| UserConstructionScript | CallFunc_K2_AttachToComponent_ReturnValue: bool, CallFunc_K2_AttachToComponent_ReturnValue_1: bool, CallFunc_K2_AttachToComponent_ReturnValue_2: bool, CallFunc_K2_AttachToComponent_ReturnValue_3: bool, CallFunc_K2_AttachToComponent_ReturnValue_4: bool, CallFunc_K2_AttachToComponent_ReturnValue_5: bool, CallFunc_K2_AttachToComponent_ReturnValue_6: bool, CallFunc_K2_AttachToComponent_ReturnValue_7: bool, CallFunc_K2_AttachToComponent_ReturnValue_8: bool, CallFunc_K2_AttachToComponent_ReturnValue_9: bool, CallFunc_K2_AttachToComponent_ReturnValue_10: bool, CallFunc_K2_AttachToComponent_ReturnValue_11: bool, CallFunc_K2_AttachToComponent_ReturnValue_12: bool, CallFunc_K2_AttachToComponent_ReturnValue_13: bool, CallFunc_K2_AttachToComponent_ReturnValue_14: bool, CallFunc_K2_AttachToComponent_ReturnValue_15: bool, CallFunc_K2_AttachToComponent_ReturnValue_16: bool, CallFunc_K2_AttachToComponent_ReturnValue_17: bool, CallFunc_K2_AttachToComponent_ReturnValue_18: bool, CallFunc_K2_AttachToComponent_ReturnValue_19: bool | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float, CallFunc_Greater_FloatFloat_ReturnValue: bool | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_Greater_FloatFloat_ReturnValue: bool, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, CallFunc_HasAuthority_ReturnValue: bool, CallFunc_GetAllActorsWithInterface_OutActors: TArray, CallFunc_Array_Get_Item: AActor*, CallFunc_Array_Length_ReturnValue: int32, K2Node_DynamicCast_AsRefresh_Physics_Interface: TScriptInterface, K2Node_DynamicCast_bSuccess: bool, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_RefreshPhysics_true: bool, CallFunc_GetDistanceTo_ReturnValue: float, CallFunc_LessEqual_FloatFloat_ReturnValue: bool | void |
| OnRep_cut | none | void |
| OnRep_destroyed | none | void |
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
| Taser | secs: float, true: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_Subtract_IntInt_ReturnValue_1: int32, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_GreaterEqual_IntInt_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue_1: int32, CallFunc_getCurrentMlmReward_dollar: int32, CallFunc_Add_IntInt_ReturnValue_2: int32, CallFunc_Subtract_IntInt_ReturnValue_2: int32, CallFunc_Subtract_IntInt_ReturnValue_3: int32, CallFunc_Greater_IntInt_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue_4: int32, CallFunc_Greater_IntInt_ReturnValue_2: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_3: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_4: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool, Temp_int_Variable: int32, Temp_int_Variable_1: int32, Temp_int_Variable_2: int32, Temp_int_Variable_3: int32, Temp_int_Variable_4: int32, Temp_int_Variable_5: int32, CallFunc_GetGameState_ReturnValue: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Greater_IntInt_ReturnValue_3: bool, CallFunc_Add_IntInt_ReturnValue_3: int32, CallFunc_Add_IntInt_ReturnValue_4: int32, CallFunc_GetTransform_ReturnValue: FTransform, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_GetMaterial_ReturnValue: UMaterialInterface*, CallFunc_GetMeshIdMatInterface_zone: TEnumAsByte<ZoneEnum>, CallFunc_GetMeshIdMatInterface_idRow: int32, CallFunc_FinishSpawningActor_ReturnValue: APlayerAI_Rob_C*, K2Node_DynamicCast_AsAI_VIP: AAI_VIP_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanAND_ReturnValue_4: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_SelectFloat_ReturnValue: float, K2Node_DynamicCast_AsAI_VIP: AAI_VIP_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_SelectFloat_ReturnValue_1: float | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, K2Node_MakeStruct_FormatArgumentData: FFormatArgumentData, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, K2Node_MakeArray_Array: TArray, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_Format_ReturnValue: FText, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_GreaterEqual_IntInt_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue_2: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_3: bool, CallFunc_BooleanAND_ReturnValue_4: bool, CallFunc_Greater_IntInt_ReturnValue_3: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_4: bool, CallFunc_Not_PreBool_ReturnValue_3: bool, CallFunc_Not_PreBool_ReturnValue_4: bool, CallFunc_BooleanAND_ReturnValue_5: bool, CallFunc_BooleanAND_ReturnValue_6: bool, CallFunc_BooleanAND_ReturnValue_7: bool, CallFunc_BooleanAND_ReturnValue_8: bool, CallFunc_Not_PreBool_ReturnValue_5: bool, CallFunc_BooleanAND_ReturnValue_9: bool, CallFunc_BooleanAND_ReturnValue_10: bool, CallFunc_Not_PreBool_ReturnValue_6: bool, CallFunc_BooleanAND_ReturnValue_11: bool, CallFunc_BooleanAND_ReturnValue_12: bool, CallFunc_BooleanAND_ReturnValue_13: bool, CallFunc_Not_PreBool_ReturnValue_7: bool, CallFunc_Not_PreBool_ReturnValue_8: bool, CallFunc_BooleanAND_ReturnValue_14: bool, K2Node_DynamicCast_AsAI_VIP: AAI_VIP_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_BooleanAND_ReturnValue_15: bool, CallFunc_Not_PreBool_ReturnValue_9: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_10: bool, CallFunc_BooleanAND_ReturnValue_16: bool, CallFunc_BooleanAND_ReturnValue_17: bool | void |
| ToggleThermal | on?: bool, true: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, dmgtovest: float, playerkiller: APlayerChar_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_GetOwner_ReturnValue: AActor*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, K2Node_DynamicCast_AsPlayer_Char_1: APlayerChar_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_GetOwner_ReturnValue_1: AActor*, K2Node_DynamicCast_AsPlayer_Char_2: APlayerChar_C*, K2Node_DynamicCast_bSuccess_2: bool, CallFunc_GetDisplayName_ReturnValue_1: FString, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess_3: bool, K2Node_DynamicCast_AsPlayer_Char_3: APlayerChar_C*, K2Node_DynamicCast_bSuccess_4: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_Multiply_FloatFloat_ReturnValue: float, CallFunc_Multiply_FloatFloat_ReturnValue_1: float, Temp_int_Variable: int32, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_HasAuthority_ReturnValue: bool, CallFunc_UtcNow_ReturnValue: FDateTime, K2Node_MakeStruct_DeathInfo: FDeathInfo__pf1458230002, CallFunc_IsValid_ReturnValue_1: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_Greater_FloatFloat_ReturnValue: bool, Temp_int_Variable_1: int32, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_VSize_ReturnValue: float, CallFunc_LessEqual_FloatFloat_ReturnValue_1: bool, CallFunc_SelectFloat_ReturnValue: float, CallFunc_SelectFloat_ReturnValue_1: float, CallFunc_Subtract_FloatFloat_ReturnValue: float, CallFunc_Subtract_FloatFloat_ReturnValue_1: float, CallFunc_Subtract_FloatFloat_ReturnValue_2: float, CallFunc_FMax_ReturnValue: float, CallFunc_Subtract_FloatFloat_ReturnValue_3: float, CallFunc_GetGameState_ReturnValue: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess_5: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue_1: bool, CallFunc_GetGameState_ReturnValue_1: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS_1: AHeistGS_C*, K2Node_DynamicCast_bSuccess_6: bool, CallFunc_LessEqual_FloatFloat_ReturnValue_2: bool, CallFunc_GetGameInstance_ReturnValue: UGameInstance*, K2Node_DynamicCast_AsHeist_GI: UHeistGI_C*, K2Node_DynamicCast_bSuccess_7: bool, CallFunc_Add_IntInt_ReturnValue_1: int32, CallFunc_IsValid_ReturnValue_2: bool, CallFunc_GetDisplayName_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_getAlivePlayersFromTeams_CopsAlive: TArray, CallFunc_getAlivePlayersFromTeams_CopsNum: int32, CallFunc_getAlivePlayersFromTeams_RobsAlive: TArray, CallFunc_getAlivePlayersFromTeams_RobsNum: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_UtcNow_ReturnValue_1: FDateTime, CallFunc_GetGameMode_ReturnValue: AGameModeBase*, K2Node_MakeStruct_DeathInfo_1: FDeathInfo__pf1458230002, K2Node_DynamicCast_AsHeist_GM: AHeistGM_C*, K2Node_DynamicCast_bSuccess_8: bool | void |
| OnRep_useAvoid? | none | void |
| OnRep_vested? | none | void |
| OnRep_tasered? | none | void |
| OnRep_RotRateZ | CallFunc_MakeRotator_ReturnValue: FRotator | void |
| OnRep_roped? | none | void |
| SetClothingMats | CallFunc_GetPlayerCharacter_ReturnValue: ACharacter*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Conv_ByteToString_ReturnValue: FString, CallFunc_Conv_StringToName_ReturnValue: FName, CallFunc_GetDataTableRowFromName_OutRow: FClothingStruct__pf1458230002, CallFunc_GetDataTableRowFromName_ReturnValue: bool | void |
| OnRep_ClothingID | none | void |
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
| getPaintingValue | easel: ACanvasEasel_C*, preventPaint: bool, paintingName: FText, paintingDescr: FText, value: int32, traceOffset: FVector | void |
| GetAiInteractTraceLocation | offset: FVector | void |
| PlayerAiCanInteract | prevent?: bool | void |
| PlayerAiInteract | playerai: APlayerAI_C*, true: bool, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool | void |
| PlayerAiInteractTimer | playerai: APlayerAI_C*, secs: float | void |
| GetAiInteractWorldLoc | worldLoc: FVector, CallFunc_K2_GetComponentLocation_ReturnValue: FVector | void |
| CopInter? | shouldInter?: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, Temp_bool_Variable: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_2: bool, Temp_text_Variable: FText, Temp_text_Variable_1: FText, CallFunc_Not_PreBool_ReturnValue_1: bool, K2Node_Select_Default: FText, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_SelectString_ReturnValue: FString | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_getCurrentMaskInfo_fasterInteract: bool, CallFunc_getCurrentMaskInfo_hpReg: bool, CallFunc_getCurrentMaskInfo_fasterSprintMoney: bool, CallFunc_getCurrentMaskInfo_reduceHpTick: bool, CallFunc_getCurrentMaskInfo_interestMoneybag: bool, CallFunc_getCurrentMaskInfo_reduceFallDmg: bool, CallFunc_getCurrentMaskInfo_reduceExplDmg: bool, CallFunc_getCurrentMaskInfo_fasterBags: bool, CallFunc_getCurrentMaskInfo_newbomb: bool, CallFunc_getCurrentMaskInfo_canttakeoff: bool, CallFunc_getCurrentMaskInfo_cdr: float, CallFunc_getCurrentMaskInfo_doubleJump_: bool, CallFunc_getCurrentMaskInfo_invisForCCTV_: bool, CallFunc_getCurrentMaskInfo_gainAmmo_: bool, CallFunc_getCurrentMaskInfo_canRide_: bool, CallFunc_getCurrentMaskInfo_slowFall_: bool, CallFunc_getCurrentMaskInfo_FoodOnMoneyPickup_: bool, CallFunc_getCurrentMaskInfo_fasterBodyCarry: bool, CallFunc_getCurrentMaskInfo_spawnMoney_: bool, CallFunc_getCurrentMaskInfo_noPoisonDmg_: bool, CallFunc_getCurrentMaskInfo_chargeJump: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_GetController_ReturnValue: AController*, CallFunc_BooleanAND_ReturnValue_1: bool, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_GetGameInstance_ReturnValue: UGameInstance*, CallFunc_Not_PreBool_ReturnValue_1: bool, K2Node_DynamicCast_AsHeist_GI: UHeistGI_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_GetGameState_ReturnValue: AGameStateBase*, CallFunc_FTrunc_ReturnValue: int32, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess_2: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_LessEqual_IntInt_ReturnValue: bool | void |
| OnRep_smoke? | none | void |
| OnRep_opened? | CallFunc_GetTransform_ReturnValue: FTransform, CallFunc_GetPlayerPawn_ReturnValue: APawn*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_FinishSpawningActor_ReturnValue: APingAct_C*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_GetGameState_ReturnValue: AGameStateBase*, CallFunc_K2_GetActorLocation_ReturnValue: FVector, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess_1: bool | void |
| destroyedCl | CallFunc_GetTransform_ReturnValue: FTransform, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_FinishSpawningActor_ReturnValue: ASafeDoorDestructible_C* | void |
| OnRep_bombPlanted? | none | void |
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
| LosCheck | startLoc: FVector, ignores: TArray, hasLos?: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_Conv_VectorToString_ReturnValue: FString, CallFunc_VSize_ReturnValue: float, CallFunc_VSize_ReturnValue_1: float, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_Conv_FloatToString_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Conv_FloatToString_ReturnValue_2: FString, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Conv_BoolToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Not_PreBool_ReturnValue_3: bool, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanOR_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_SelectString_ReturnValue: FString, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_VSize_ReturnValue: float, CallFunc_VSize_ReturnValue_1: float, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_Not_PreBool_ReturnValue_3: bool, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_4: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float, CallFunc_SelectFloat_ReturnValue: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_GetController_ReturnValue: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, K2Node_MakeArray_Array: TArray, CallFunc_GetGameMode_ReturnValue: AGameModeBase*, CallFunc_HasAuthority_ReturnValue: bool, K2Node_DynamicCast_AsHeist_GM: AHeistGM_C*, K2Node_DynamicCast_bSuccess_2: bool, CallFunc_ClosestActorOfClass_closest: AActor*, CallFunc_ClosestActorOfClass_dist: float, CallFunc_ClosestActorOfClass_valid: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, K2Node_DynamicCast_AsPlayer_AI_Cop: APlayerAI_Cop_C*, K2Node_DynamicCast_bSuccess_3: bool, CallFunc_LessEqual_FloatFloat_ReturnValue_1: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float, CallFunc_Subtract_FloatFloat_ReturnValue_1: float, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_VSize_ReturnValue: float, CallFunc_VSize_ReturnValue_1: float, CallFunc_Less_FloatFloat_ReturnValue: bool | void |
| OnRep_armorOutside? | none | void |
| OnRep_armorInside? | none | void |
| OnRep_destroyed | none | void |
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
| EmpStart | duration: float, true: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, Temp_int_Variable: int32, CallFunc_K2_GetComponentToWorld_ReturnValue: FTransform, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_FinishSpawningActor_ReturnValue: AProximityMine_C*, CallFunc_BooleanAND_ReturnValue_2: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool, CallFunc_GetPlayerPawn_ReturnValue: APawn*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_3: bool | void |
| OnRep_emp? | CallFunc_BooleanOR_ReturnValue: bool, K2Node_DynamicCast_AsChameleon: AChameleon_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_BooleanOR_ReturnValue_1: bool, CallFunc_SelectFloat_ReturnValue: float, CallFunc_Conv_BoolToString_ReturnValue: FString, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString | void |
| OnRep_brokenTemp? | CallFunc_BooleanOR_ReturnValue: bool, K2Node_DynamicCast_AsChameleon: AChameleon_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_BooleanOR_ReturnValue_1: bool, CallFunc_SelectFloat_ReturnValue: float, CallFunc_Conv_BoolToString_ReturnValue: FString, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString | void |
| OnRep_broken? | CallFunc_BooleanOR_ReturnValue: bool, K2Node_DynamicCast_AsChameleon: AChameleon_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_SelectFloat_ReturnValue: float | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, Temp_int_Variable: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FClamp_ReturnValue: float, CallFunc_Subtract_IntInt_ReturnValue: int32 | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| OnRep_uses? | none | void |
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
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_IsActorBeingDestroyed_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool | void |

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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_IsActorBeingDestroyed_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| EmpStart | duration: float, true: bool | void |
| OnRep_emp? | CallFunc_Not_PreBool_ReturnValue: bool | void |
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
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_GetOwner_ReturnValue: AActor*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText | void |
| ExplodeSV | alreadyDmged: TArray, Temp_int_Array_Index_Variable: int32, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Loop_Counter_Variable_1: int32, CallFunc_Add_IntInt_ReturnValue_1: int32, Temp_int_Array_Index_Variable_1: int32, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_GetOverlappingActors_OverlappingActors: TArray, CallFunc_Array_Get_Item: AActor*, CallFunc_Array_Length_ReturnValue: int32, K2Node_DynamicCast_AsDamage_Interface: TScriptInterface, K2Node_DynamicCast_bSuccess: bool, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_GetDistanceTo_ReturnValue: float, CallFunc_Divide_FloatFloat_ReturnValue: float, CallFunc_Array_Contains_ReturnValue: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float, CallFunc_FClamp_ReturnValue: float, CallFunc_Multiply_FloatFloat_ReturnValue: float, CallFunc_DealDmg_dead: bool, CallFunc_GetOverlappingActors_OverlappingActors_1: TArray, CallFunc_Array_Get_Item_1: AActor*, CallFunc_Array_Length_ReturnValue_1: int32, K2Node_DynamicCast_AsLos_Interface: TScriptInterface, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_Less_IntInt_ReturnValue_1: bool, K2Node_DynamicCast_AsDamage_Interface_1: TScriptInterface, K2Node_DynamicCast_bSuccess_2: bool, CallFunc_DealDmg_dead_1: bool, K2Node_MakeArray_Array: TArray, CallFunc_LosCheck_hasLos_: bool, CallFunc_DoesImplementInterface_ReturnValue: bool, K2Node_MakeArray_Array_1: TArray, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, CallFunc_NotEqual_ObjectObject_ReturnValue: bool, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, CallFunc_BreakHitResult_bBlockingHit: bool, CallFunc_BreakHitResult_bInitialOverlap: bool, CallFunc_BreakHitResult_Time: float, CallFunc_BreakHitResult_Distance: float, CallFunc_BreakHitResult_Location: FVector, CallFunc_BreakHitResult_ImpactPoint: FVector, CallFunc_BreakHitResult_Normal: FVector, CallFunc_BreakHitResult_ImpactNormal: FVector, CallFunc_BreakHitResult_PhysMat: UPhysicalMaterial*, CallFunc_BreakHitResult_HitActor: AActor*, CallFunc_BreakHitResult_HitComponent: UPrimitiveComponent*, CallFunc_BreakHitResult_HitBoneName: FName, CallFunc_BreakHitResult_HitItem: int32, CallFunc_BreakHitResult_FaceIndex: int32, CallFunc_BreakHitResult_TraceStart: FVector, CallFunc_BreakHitResult_TraceEnd: FVector, CallFunc_Array_Add_ReturnValue: int32, CallFunc_GetDisplayName_ReturnValue: FString | void |
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
| VisColl | l1: FVector, l2: FVector, blocked?: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_LineIntersectsSphere_blocked_: bool | void |
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
| ToggleDrillPlacementGuide | active?: bool, true?: bool, Temp_bool_Variable: bool, Temp_byte_Variable: TEnumAsByte<ECollisionEnabled::Type>, Temp_byte_Variable_1: TEnumAsByte<ECollisionEnabled::Type>, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, K2Node_Select_Default: TEnumAsByte<ECollisionEnabled::Type> | void |
| ToggleDrillPreview | active?: bool, true?: bool | void |
| PlaceDrill | place?: bool, true?: bool, Temp_bool_Variable: bool, Temp_byte_Variable: TEnumAsByte<ECollisionEnabled::Type>, Temp_byte_Variable_1: TEnumAsByte<ECollisionEnabled::Type>, CallFunc_ToggleDrillPlacementGuide_true_: bool, K2Node_Select_Default: TEnumAsByte<ECollisionEnabled::Type>, K2Node_DynamicCast_AsDrill_for_Floor: ADrillForFloor_C*, K2Node_DynamicCast_bSuccess: bool | void |
| updateBroken | broken?: bool, Temp_bool_Variable: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, Temp_byte_Variable: TEnumAsByte<ECollisionEnabled::Type>, Temp_byte_Variable_1: TEnumAsByte<ECollisionEnabled::Type>, K2Node_Select_Default: TEnumAsByte<ECollisionEnabled::Type>, CallFunc_HasAuthority_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_IsValid_ReturnValue_1: bool, CallFunc_K2_GetComponentToWorld_ReturnValue: FTransform, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_FinishSpawningActor_ReturnValue: ALadderAct_C*, CallFunc_BreakTransform_Location: FVector, CallFunc_BreakTransform_Rotation: FRotator, CallFunc_BreakTransform_Scale: FVector | void |
| OnRep_finished? | none | void |
| OnRep_drillPlaced? | Temp_bool_Variable: bool, Temp_byte_Variable: TEnumAsByte<ECollisionEnabled::Type>, Temp_byte_Variable_1: TEnumAsByte<ECollisionEnabled::Type>, CallFunc_ToggleDrillPlacementGuide_true_: bool, K2Node_DynamicCast_AsDrill_for_Floor: ADrillForFloor_C*, K2Node_DynamicCast_bSuccess: bool, K2Node_Select_Default: TEnumAsByte<ECollisionEnabled::Type> | void |
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
| getPaintingValue | easel: ACanvasEasel_C*, preventPaint: bool, paintingName: FText, paintingDescr: FText, value: int32, traceOffset: FVector, CallFunc_Not_PreBool_ReturnValue: bool | void |
| GetAiInteractTraceLocation | offset: FVector | void |
| PlayerAiCanInteract | prevent?: bool | void |
| CopInter? | shouldInter?: bool | void |
| PlayerAiInteract | playerai: APlayerAI_C*, true: bool | void |
| PlayerAiInteractTimer | playerai: APlayerAI_C*, secs: float | void |
| GetAiInteractWorldLoc | worldLoc: FVector, Temp_object_Variable: TArray, Temp_object_Variable_1: TArray, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_2: FVector, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, CallFunc_K2_GetComponentLocation_ReturnValue_3: FVector, CallFunc_BreakHitResult_bBlockingHit: bool, CallFunc_BreakHitResult_bInitialOverlap: bool, CallFunc_BreakHitResult_Time: float, CallFunc_BreakHitResult_Distance: float, CallFunc_BreakHitResult_Location: FVector, CallFunc_BreakHitResult_ImpactPoint: FVector, CallFunc_BreakHitResult_Normal: FVector, CallFunc_BreakHitResult_ImpactNormal: FVector, CallFunc_BreakHitResult_PhysMat: UPhysicalMaterial*, CallFunc_BreakHitResult_HitActor: AActor*, CallFunc_BreakHitResult_HitComponent: UPrimitiveComponent*, CallFunc_BreakHitResult_HitBoneName: FName, CallFunc_BreakHitResult_HitItem: int32, CallFunc_BreakHitResult_FaceIndex: int32, CallFunc_BreakHitResult_TraceStart: FVector, CallFunc_BreakHitResult_TraceEnd: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_4: FVector, CallFunc_LineTraceSingle_OutHit_1: FHitResult, CallFunc_LineTraceSingle_ReturnValue_1: bool, CallFunc_BreakHitResult_bBlockingHit_1: bool, CallFunc_BreakHitResult_bInitialOverlap_1: bool, CallFunc_BreakHitResult_Time_1: float, CallFunc_BreakHitResult_Distance_1: float, CallFunc_BreakHitResult_Location_1: FVector, CallFunc_BreakHitResult_ImpactPoint_1: FVector, CallFunc_BreakHitResult_Normal_1: FVector, CallFunc_BreakHitResult_ImpactNormal_1: FVector, CallFunc_BreakHitResult_PhysMat_1: UPhysicalMaterial*, CallFunc_BreakHitResult_HitActor_1: AActor*, CallFunc_BreakHitResult_HitComponent_1: UPrimitiveComponent*, CallFunc_BreakHitResult_HitBoneName_1: FName, CallFunc_BreakHitResult_HitItem_1: int32, CallFunc_BreakHitResult_FaceIndex_1: int32, CallFunc_BreakHitResult_TraceStart_1: FVector, CallFunc_BreakHitResult_TraceEnd_1: FVector | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_GetParentActor_ReturnValue: AActor*, CallFunc_SelectString_ReturnValue: FString, K2Node_DynamicCast_AsDrillable_Floor: ADrillableFloor_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Not_PreBool_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_ClosestActToLoc_closest: AActor*, CallFunc_ClosestActToLoc_dist: float, CallFunc_ClosestActToLoc_valid: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| OnRep_running? | CallFunc_SelectFloat_ReturnValue: float | void |

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
| getPaintingValue | easel: ACanvasEasel_C*, preventPaint: bool, paintingName: FText, paintingDescr: FText, value: int32, traceOffset: FVector, CallFunc_NotEqual_ObjectObject_ReturnValue: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| RefreshPhysics | true: bool | void |
| InteractClAlt | PlayerChar: APlayerChar_C*, true: bool | void |
| ClTimer | char: APlayerChar_C*, secs: float, CallFunc_isClass__is_: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractCl | PlayerChar: APlayerChar_C*, true: bool | void |
| GetAltInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_IsValid_ReturnValue_1: bool, CallFunc_GetName_name: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_IsValid_ReturnValue_2: bool, CallFunc_GetName_name_1: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_IsValid_ReturnValue_3: bool, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_IsValid_ReturnValue_4: bool, CallFunc_SelectString_ReturnValue: FString | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_isClass__is_: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_NotEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_3: bool, CallFunc_fired__fired: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_GetGameTimeSinceCreation_ReturnValue: float, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_IsValid_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_IsValid_ReturnValue_2: bool, CallFunc_lastCarrierCop__lastCarrierCop_: bool, CallFunc_lastCarrierCop__lastCarrierRob_: bool, CallFunc_killedByCop__killedByCop: bool, CallFunc_killedByCop__killedByRob: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_3: bool | void |
| fired? | fired: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool | void |
| InteractAltSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, OldPlayerMat: UMaterialInterface*, OldPlayerMesh: USkeletalMesh*, CallFunc_GetMaterial_ReturnValue: UMaterialInterface*, CallFunc_GetMaterial_ReturnValue_1: UMaterialInterface* | void |
| UpdateMeshMat | none | void |
| OnRep_MeshMaterial | none | void |
| OnRep_Mesh | none | void |
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
| GetAiInteractTraceLocation | offset: FVector | void |
| PlayerAiCanInteract | prevent?: bool | void |
| PlayerAiInteract | playerai: APlayerAI_C*, true: bool, OldPlayerMat: UMaterialInterface*, OldPlayerMesh: USkeletalMesh*, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_GetMaterial_ReturnValue: UMaterialInterface*, K2Node_DynamicCast_AsMaterial: UMaterial*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_GetMeshId_zone: TEnumAsByte<ZoneEnum>, CallFunc_GetMeshId_idRow: int32 | void |
| PlayerAiInteractTimer | playerai: APlayerAI_C*, secs: float | void |
| GetAiInteractWorldLoc | worldLoc: FVector | void |
| CopInter? | shouldInter?: bool | void |
| TimerAlt | timer: float, retry: bool | void |
| InteractAltSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_canCarryBodies__can_: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_IsValid_ReturnValue_1: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, OldPlayerRadiation: float, OldPlayerMat: UMaterialInterface*, OldPlayerMesh: USkeletalMesh*, CallFunc_GetMeshZone_zone: TEnumAsByte<ZoneEnum>, CallFunc_GetMeshZone_clothesRow: FName, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_isClass__is_: bool, CallFunc_FMax_ReturnValue: float, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FMin_ReturnValue: float, CallFunc_GreaterEqual_FloatFloat_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue_1: float, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue_1: int32, CallFunc_GetController_ReturnValue: AController*, CallFunc_EqualEqual_ByteByte_ReturnValue_3: bool, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_GetMaterial_ReturnValue: UMaterialInterface*, Temp_int_Variable: int32, Temp_int_Variable_1: int32, Temp_int_Variable_2: int32, CallFunc_lastCarrierCop__lastCarrierCop_: bool, CallFunc_lastCarrierCop__lastCarrierRob_: bool, CallFunc_killedByCop__killedByCop: bool, CallFunc_killedByCop__killedByRob: bool, CallFunc_GetGameTimeSinceCreation_ReturnValue: float, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_GetGameMode_ReturnValue: AGameModeBase*, K2Node_DynamicCast_AsHeist_GM: AHeistGM_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_K2_GetRandomReachablePointInRadius_RandomLocation: FVector, CallFunc_K2_GetRandomReachablePointInRadius_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_Add_VectorVector_ReturnValue: FVector, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_MakeTransform_ReturnValue: FTransform, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_FinishSpawningActor_ReturnValue: APlayerAI_Cop_C*, CallFunc_IsValid_ReturnValue_1: bool, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess_2: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_4: bool, CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_GetGameMode_ReturnValue_1: AGameModeBase*, K2Node_DynamicCast_AsTutorial_GM: ATutorialGM_C*, K2Node_DynamicCast_bSuccess_3: bool, CallFunc_GetGameState_ReturnValue: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess_4: bool, CallFunc_GetEnumeratorUserFriendlyName_ReturnValue: FString, CallFunc_Add_IntInt_ReturnValue_2: int32, CallFunc_GetEnumeratorUserFriendlyName_ReturnValue_1: FString, CallFunc_Left_ReturnValue: FString, CallFunc_UtcNow_ReturnValue: FDateTime, CallFunc_EqualEqual_StrStr_ReturnValue: bool, CallFunc_Subtract_DateTimeDateTime_ReturnValue: FTimespan, CallFunc_SelectString_ReturnValue: FString, CallFunc_GetTotalSeconds_ReturnValue: float, CallFunc_FTrunc_ReturnValue: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_3: FString | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| lastCarrierCop? | lastCarrierCop?: bool, lastCarrierRob?: bool, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool | void |
| killedByCop? | killedByCop: bool, killedByRob: bool, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool | void |
| OnRep_deathInfo | CallFunc_IsValid_ReturnValue: bool | void |
| OnRep_MeshMaterial | CallFunc_IsValid_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| OnRep_Mesh | CallFunc_IsValid_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
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
| GetAiInteractTraceLocation | offset: FVector | void |
| PlayerAiCanInteract | prevent?: bool | void |
| PlayerAiInteract | playerai: APlayerAI_C*, true: bool, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_HasAuthority_ReturnValue: bool | void |
| PlayerAiInteractTimer | playerai: APlayerAI_C*, secs: float | void |
| GetAiInteractWorldLoc | worldLoc: FVector | void |
| CopInter? | shouldInter?: bool | void |
| GetItemName | name: FString | void |
| RefreshPhysics | true: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_GetGameTimeSinceCreation_ReturnValue: float, CallFunc_isClass__is_: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_canCarryBombs__can_: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_3: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, OldPlayerMat: UMaterialInterface*, OldPlayerMesh: USkeletalMesh*, Temp_int_Variable: int32, CallFunc_isClass__is_: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_GetGameTimeSinceCreation_ReturnValue: float, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_GetGameMode_ReturnValue: AGameModeBase*, K2Node_DynamicCast_AsTutorial_GM: ATutorialGM_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_Array_Get_Item: ACopCar_C*, CallFunc_IsValid_ReturnValue: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_MakeTransform_ReturnValue: FTransform, CallFunc_GetDistanceTo_ReturnValue: float, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_FinishSpawningActor_ReturnValue: ABombBag_C* | void |
| GetCustomTrace | Hit: FHitResult | void |
| GetCustomPingSettings | Executor: APawn*, Icon: FName, Conditions: TArray | void |
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
| GetRadiation | loc: FVector, power: float | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| GetAiInteractTraceLocation | offset: FVector | void |
| PlayerAiCanInteract | prevent?: bool | void |
| PlayerAiInteract | playerai: APlayerAI_C*, true: bool, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FMin_ReturnValue: float, CallFunc_Add_IntInt_ReturnValue: int32 | void |
| PlayerAiInteractTimer | playerai: APlayerAI_C*, secs: float | void |
| GetAiInteractWorldLoc | worldLoc: FVector | void |
| CopInter? | shouldInter?: bool | void |
| GetItemName | name: FString | void |
| RefreshPhysics | true: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_GetGameTimeSinceCreation_ReturnValue: float, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_isClass__is_: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_canCarryMoney__can_: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_Conv_IntToText_ReturnValue: FText, K2Node_MakeStruct_FormatArgumentData: FFormatArgumentData, CallFunc_Conv_IntToString_ReturnValue: FString, K2Node_MakeArray_Array: TArray, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Format_ReturnValue: FText, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Conv_IntToString_ReturnValue_1: FString, CallFunc_Conv_StringToText_ReturnValue: FText, CallFunc_Concat_StrStr_ReturnValue_2: FString, K2Node_MakeStruct_FormatArgumentData_1: FFormatArgumentData, CallFunc_Concat_StrStr_ReturnValue_3: FString, K2Node_MakeArray_Array_1: TArray, CallFunc_Format_ReturnValue_1: FText, CallFunc_Conv_IntToText_ReturnValue_1: FText, K2Node_MakeStruct_FormatArgumentData_2: FFormatArgumentData, CallFunc_Conv_IntToString_ReturnValue_2: FString, K2Node_MakeArray_Array_2: TArray, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_Format_ReturnValue_2: FText, CallFunc_Concat_StrStr_ReturnValue_5: FString | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool, CallFunc_isClass__is_: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, OldPlayerMat: UMaterialInterface*, OldPlayerMesh: USkeletalMesh*, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_isClass__is_: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_GetGameTimeSinceCreation_ReturnValue: float, CallFunc_FMin_ReturnValue: float, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_canCarryMoney__can_: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue_1: int32, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_IsActorBeingDestroyed_ReturnValue: bool, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Add_IntInt_ReturnValue_2: int32 | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_GetGameState_ReturnValue: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_GreaterEqual_IntInt_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_BooleanAND_ReturnValue_1: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_GetGameMode_ReturnValue: AGameModeBase*, K2Node_DynamicCast_AsHeist_GM: AHeistGM_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FClamp_ReturnValue: float, CallFunc_GetGameState_ReturnValue: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_GreaterEqual_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool, CallFunc_GetGameState_ReturnValue: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_GreaterEqual_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| OnRep_moving? | none | void |
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
| GetRadiation | loc: FVector, power: float | void |
| GetAiInteractTraceLocation | offset: FVector | void |
| PlayerAiCanInteract | prevent?: bool, CallFunc_IsValid_ReturnValue: bool | void |
| PlayerAiInteract | playerai: APlayerAI_C*, true: bool, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_HasAuthority_ReturnValue: bool, CallFunc_HasAuthority_ReturnValue_1: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FMin_ReturnValue: float, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_ClosestActToLoc_closest: AActor*, CallFunc_ClosestActToLoc_dist: float, CallFunc_ClosestActToLoc_valid: bool, K2Node_DynamicCast_AsMoney_Jewels: AMoneyJewels_C*, K2Node_DynamicCast_bSuccess_1: bool, K2Node_DynamicCast_AsJewels_Case: AJewelsCase_C*, K2Node_DynamicCast_bSuccess_2: bool, CallFunc_Add_IntInt_ReturnValue: int32 | void |
| PlayerAiInteractTimer | playerai: APlayerAI_C*, secs: float | void |
| GetAiInteractWorldLoc | worldLoc: FVector | void |
| CopInter? | shouldInter?: bool | void |
| GetItemName | name: FString, CallFunc_Conv_TextToString_ReturnValue: FString | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, Temp_text_Variable: FText, CallFunc_isClass_is: bool, CallFunc_GetActorScale3D_ReturnValue: FVector, CallFunc_BreakVector_X: float, CallFunc_BreakVector_Y: float, CallFunc_BreakVector_Z: float, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, K2Node_DynamicCast_AsMoney_Top_Secret: AMoneyTopSecret_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_Conv_IntToText_ReturnValue: FText, K2Node_MakeStruct_FormatArgumentData: FFormatArgumentData, CallFunc_canCarryMoney__can_: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_EqualEqual_FloatFloat_ReturnValue: bool, Temp_text_Variable_1: FText, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanAND_ReturnValue_4: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_BooleanOR_ReturnValue_1: bool, K2Node_MakeStruct_FormatArgumentData_1: FFormatArgumentData, CallFunc_BooleanAND_ReturnValue_5: bool, K2Node_MakeArray_Array: TArray, CallFunc_Conv_TextToString_ReturnValue: FString, CallFunc_Format_ReturnValue: FText, CallFunc_Concat_StrStr_ReturnValue: FString, Temp_bool_Variable: bool, K2Node_Select_Default: FText | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool, CallFunc_GetPlayerPawn_ReturnValue: APawn*, CallFunc_Divide_FloatFloat_ReturnValue: float, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_SelectFloat_ReturnValue: float | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_isClass_is: bool, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_getCurrentMaskInfo_fasterInteract: bool, CallFunc_getCurrentMaskInfo_hpReg: bool, CallFunc_getCurrentMaskInfo_fasterSprintMoney: bool, CallFunc_getCurrentMaskInfo_reduceHpTick: bool, CallFunc_getCurrentMaskInfo_interestMoneybag: bool, CallFunc_getCurrentMaskInfo_reduceFallDmg: bool, CallFunc_getCurrentMaskInfo_reduceExplDmg: bool, CallFunc_getCurrentMaskInfo_fasterBags: bool, CallFunc_getCurrentMaskInfo_newbomb: bool, CallFunc_getCurrentMaskInfo_canttakeoff: bool, CallFunc_getCurrentMaskInfo_cdr: float, CallFunc_getCurrentMaskInfo_doubleJump_: bool, CallFunc_getCurrentMaskInfo_invisForCCTV_: bool, CallFunc_getCurrentMaskInfo_gainAmmo_: bool, CallFunc_getCurrentMaskInfo_canRide_: bool, CallFunc_getCurrentMaskInfo_slowFall_: bool, CallFunc_getCurrentMaskInfo_FoodOnMoneyPickup_: bool, CallFunc_getCurrentMaskInfo_fasterBodyCarry: bool, CallFunc_getCurrentMaskInfo_spawnMoney_: bool, CallFunc_getCurrentMaskInfo_noPoisonDmg_: bool, CallFunc_getCurrentMaskInfo_chargeJump: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_3: bool, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Greater_IntInt_ReturnValue_1: bool, Temp_int_Variable: int32, K2Node_DynamicCast_AsMoney_Top_Secret: AMoneyTopSecret_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Add_IntInt_ReturnValue_1: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FMin_ReturnValue: float, CallFunc_EqualEqual_FloatFloat_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue_3: bool, K2Node_DynamicCast_AsMoney_Diamond: AMoney_Diamond_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_4: bool, CallFunc_BooleanAND_ReturnValue_4: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_5: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_5: bool, Temp_int_Variable_1: int32, CallFunc_GetTransform_ReturnValue: FTransform, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_FinishSpawningActor_ReturnValue: AHpKit_Donut_C*, CallFunc_GetTransform_ReturnValue_1: FTransform, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue_1: AActor*, CallFunc_GetGameMode_ReturnValue: AGameModeBase*, CallFunc_FinishSpawningActor_ReturnValue_1: AJokerCard_C*, K2Node_DynamicCast_AsTutorial_GM: ATutorialGM_C*, K2Node_DynamicCast_bSuccess_2: bool, CallFunc_SelectInt_ReturnValue: int32, CallFunc_Multiply_IntInt_ReturnValue: int32, CallFunc_SelectInt_ReturnValue_1: int32, CallFunc_Multiply_IntFloat_ReturnValue: float, CallFunc_FTrunc_ReturnValue: int32, CallFunc_SelectInt_ReturnValue_2: int32, CallFunc_Conv_IntToFloat_ReturnValue: float, CallFunc_Multiply_FloatFloat_ReturnValue: float, CallFunc_FTrunc_ReturnValue_1: int32, CallFunc_Add_IntInt_ReturnValue_2: int32 | void |
| PlayerInteracted | player: APlayerChar_C* | void |
| OnRep_cloaked? | Temp_bool_Variable: bool, Temp_object_Variable: USoundBase*, Temp_object_Variable_1: USoundBase*, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_IsValid_ReturnValue: bool, K2Node_Select_Default: USoundBase*, CallFunc_NotEqual_BoolBool_ReturnValue: bool, CallFunc_SpawnSoundAttached_ReturnValue: UAudioComponent* | void |
| OnRep_attachedTo | CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_SetActorLocation_SweepHitResult: FHitResult, CallFunc_K2_SetActorLocation_ReturnValue: bool | void |
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
| RestartCl | true?: bool | void |
| RestartSV | true?: bool | void |

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
| EmpStart | duration: float, true: bool, CallFunc_DealDmg_dead: bool | void |
| isSus | isSus?: bool, isSusEasy?: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, Temp_int_Variable: int32, CallFunc_K2_GetComponentToWorld_ReturnValue: FTransform, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_FinishSpawningActor_ReturnValue: AProximityMine_C*, CallFunc_BooleanAND_ReturnValue_1: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool, CallFunc_GetPlayerPawn_ReturnValue: APawn*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_HasAuthority_ReturnValue: bool, CallFunc_customDestroyedHandling_handled_: bool, CallFunc_GetController_ReturnValue: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| customDestroyedHandling | handled?: bool | void |
| OnRep_hasGymBag? | none | void |
| OnRep_hasDrillBag? | none | void |
| OnRep_attachedwepcrate | CallFunc_IsValid_ReturnValue: bool | void |
| OnRep_emp? | CallFunc_SelectFloat_ReturnValue: float | void |
| OnRep_hasBombBag? | none | void |
| OnRep_hasBag? | none | void |
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
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, Temp_int_Variable: int32, CallFunc_FMax_ReturnValue: float, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FMin_ReturnValue: float, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_GreaterEqual_FloatFloat_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue_1: float, CallFunc_Add_IntInt_ReturnValue: int32 | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_HasAuthority_ReturnValue: bool | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, Temp_int_Variable: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_IsValid_ReturnValue_1: bool, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_Less_FloatFloat_ReturnValue_1: bool, CallFunc_GreaterEqual_IntInt_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_Greater_IntInt_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| OnRep_remainingVests | CallFunc_GreaterEqual_IntInt_ReturnValue: bool | void |
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
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float, CallFunc_Greater_FloatFloat_ReturnValue: bool | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_HasAuthority_ReturnValue: bool | void |
| OnRep_cut | none | void |
| OnRep_destroyed | none | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_FMax_ReturnValue: float, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FMin_ReturnValue: float, CallFunc_GreaterEqual_FloatFloat_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue_1: float, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, Temp_int_Variable: int32, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| isSus | isSus?: bool, isSusEasy?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_HasAuthority_ReturnValue: bool, CallFunc_GetController_ReturnValue: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
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
| getPaintingValue | easel: ACanvasEasel_C*, preventPaint: bool, paintingName: FText, paintingDescr: FText, value: int32, traceOffset: FVector | void |
| GetAiInteractTraceLocation | offset: FVector | void |
| PlayerAiCanInteract | prevent?: bool | void |
| CopInter? | shouldInter?: bool | void |
| GetAiInteractWorldLoc | worldLoc: FVector, Temp_object_Variable: TArray, Temp_object_Variable_1: TArray, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, CallFunc_LineTraceSingle_OutHit_1: FHitResult, CallFunc_LineTraceSingle_ReturnValue_1: bool, CallFunc_BreakHitResult_bBlockingHit: bool, CallFunc_BreakHitResult_bInitialOverlap: bool, CallFunc_BreakHitResult_Time: float, CallFunc_BreakHitResult_Distance: float, CallFunc_BreakHitResult_Location: FVector, CallFunc_BreakHitResult_ImpactPoint: FVector, CallFunc_BreakHitResult_Normal: FVector, CallFunc_BreakHitResult_ImpactNormal: FVector, CallFunc_BreakHitResult_PhysMat: UPhysicalMaterial*, CallFunc_BreakHitResult_HitActor: AActor*, CallFunc_BreakHitResult_HitComponent: UPrimitiveComponent*, CallFunc_BreakHitResult_HitBoneName: FName, CallFunc_BreakHitResult_HitItem: int32, CallFunc_BreakHitResult_FaceIndex: int32, CallFunc_BreakHitResult_TraceStart: FVector, CallFunc_BreakHitResult_TraceEnd: FVector | void |
| PlayerAiInteract | playerai: APlayerAI_C*, true: bool | void |
| PlayerAiInteractTimer | playerai: APlayerAI_C*, secs: float | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_Not_PreBool_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_IsActorBeingDestroyed_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| VisColl | l1: FVector, l2: FVector, blocked?: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_LineIntersectsSphere_blocked_: bool | void |
| ToggleThermal | on?: bool, true: bool, CallFunc_Not_PreBool_ReturnValue: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| traceFromTo | actorLoc: FVector, ourLoc: FVector, ActorsToIgnore: TArray, blocked: bool, hit: FHitResult, CallFunc_Add_VectorVector_ReturnValue: FVector, CallFunc_Add_VectorVector_ReturnValue_1: FVector, CallFunc_SphereTraceSingle_OutHit: FHitResult, CallFunc_SphereTraceSingle_ReturnValue: bool, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, CallFunc_BreakHitResult_bBlockingHit: bool, CallFunc_BreakHitResult_bInitialOverlap: bool, CallFunc_BreakHitResult_Time: float, CallFunc_BreakHitResult_Distance: float, CallFunc_BreakHitResult_Location: FVector, CallFunc_BreakHitResult_ImpactPoint: FVector, CallFunc_BreakHitResult_Normal: FVector, CallFunc_BreakHitResult_ImpactNormal: FVector, CallFunc_BreakHitResult_PhysMat: UPhysicalMaterial*, CallFunc_BreakHitResult_HitActor: AActor*, CallFunc_BreakHitResult_HitComponent: UPrimitiveComponent*, CallFunc_BreakHitResult_HitBoneName: FName, CallFunc_BreakHitResult_HitItem: int32, CallFunc_BreakHitResult_FaceIndex: int32, CallFunc_BreakHitResult_TraceStart: FVector, CallFunc_BreakHitResult_TraceEnd: FVector, CallFunc_Vector_Distance_ReturnValue: float, CallFunc_Less_FloatFloat_ReturnValue: bool | void |
| OnRep_triggered? | CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_SpawnSoundAtLocation_ReturnValue: UAudioComponent* | void |
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
| EmpStart | duration: float, true: bool | void |
| OnRep_emp? | none | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float, CallFunc_Greater_FloatFloat_ReturnValue: bool | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_HasAuthority_ReturnValue: bool | void |
| OnRep_cut | none | void |
| OnRep_destroyed | none | void |
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
| getPaintingValue | easel: ACanvasEasel_C*, preventPaint: bool, paintingName: FText, paintingDescr: FText, value: int32, traceOffset: FVector | void |
| ToggleDrillPreview | active?: bool, true?: bool | void |
| PlaceDrill | place?: bool, true?: bool, CallFunc_GetTransform_ReturnValue: FTransform, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_IsValid_ReturnValue: bool, CallFunc_FinishSpawningActor_ReturnValue: ASafeDoor_C*, CallFunc_IsActorBeingDestroyed_ReturnValue: bool | void |
| ToggleDrillPlacementGuide | active?: bool, true?: bool | void |

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
| GetAiInteractTraceLocation | offset: FVector | void |
| PlayerAiCanInteract | prevent?: bool | void |
| PlayerAiInteract | playerai: APlayerAI_C*, true: bool, Temp_int_Variable: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_NotEqual_ByteByte_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue: int32 | void |
| PlayerAiInteractTimer | playerai: APlayerAI_C*, secs: float | void |
| GetAiInteractWorldLoc | worldLoc: FVector | void |
| CopInter? | shouldInter?: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_isClass__is_: bool, Temp_byte_Variable: uint8, CallFunc_Conv_ByteToInt_ReturnValue: int32, CallFunc_Array_Get_Item: uint8, CallFunc_Array_Contains_ReturnValue: bool, CallFunc_Conv_ByteToString_ReturnValue: FString, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Conv_StringToName_ReturnValue: FName, CallFunc_GetDataTableRowFromName_OutRow: FWeaponTypesStructs__pf3747386746, CallFunc_GetDataTableRowFromName_ReturnValue: bool, CallFunc_Conv_TextToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, Temp_int_Variable: int32, CallFunc_isClass__is_: bool, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue: int32 | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| OnRep_uses? | none | void |
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
| getPaintingValue | easel: ACanvasEasel_C*, preventPaint: bool, paintingName: FText, paintingDescr: FText, value: int32, traceOffset: FVector | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_DealDmg_self_CastInput: TScriptInterface, CallFunc_DealDmg_dead: bool, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_Multiply_FloatFloat_ReturnValue: float, CallFunc_SelectFloat_ReturnValue: float, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_IsValid_ReturnValue_1: bool, CallFunc_DealDmg_self_CastInput_1: TScriptInterface, CallFunc_DealDmg_dead_1: bool, CallFunc_Conv_FloatToString_ReturnValue_1: FString, CallFunc_GetTransform_ReturnValue: FTransform, CallFunc_Subtract_FloatFloat_ReturnValue: float, CallFunc_InverseTransformLocation_ReturnValue: FVector, CallFunc_BreakVector_X: float, CallFunc_BreakVector_Y: float, CallFunc_BreakVector_Z: float, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_Conv_FloatToString_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_3: FString | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_getCurrentMaskInfo_fasterInteract: bool, CallFunc_getCurrentMaskInfo_hpReg: bool, CallFunc_getCurrentMaskInfo_fasterSprintMoney: bool, CallFunc_getCurrentMaskInfo_reduceHpTick: bool, CallFunc_getCurrentMaskInfo_interestMoneybag: bool, CallFunc_getCurrentMaskInfo_reduceFallDmg: bool, CallFunc_getCurrentMaskInfo_reduceExplDmg: bool, CallFunc_getCurrentMaskInfo_fasterBags: bool, CallFunc_getCurrentMaskInfo_newbomb: bool, CallFunc_getCurrentMaskInfo_canttakeoff: bool, CallFunc_getCurrentMaskInfo_cdr: float, CallFunc_getCurrentMaskInfo_doubleJump_: bool, CallFunc_getCurrentMaskInfo_invisForCCTV_: bool, CallFunc_getCurrentMaskInfo_gainAmmo_: bool, CallFunc_getCurrentMaskInfo_canRide_: bool, CallFunc_getCurrentMaskInfo_slowFall_: bool, CallFunc_getCurrentMaskInfo_FoodOnMoneyPickup_: bool, CallFunc_getCurrentMaskInfo_fasterBodyCarry: bool, CallFunc_getCurrentMaskInfo_spawnMoney_: bool, CallFunc_getCurrentMaskInfo_noPoisonDmg_: bool, CallFunc_getCurrentMaskInfo_chargeJump: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_GetController_ReturnValue: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_GetController_ReturnValue_1: AController*, K2Node_DynamicCast_AsHeist_PC_1: AHeistPC_C*, K2Node_DynamicCast_bSuccess_1: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| isCapsuleFree | caps: UCapsuleComponent*, slim: bool, free: bool, Temp_object_Variable: TArray, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_GetScaledCapsuleRadius_ReturnValue: float, CallFunc_GetScaledCapsuleHalfHeight_ReturnValue: float, CallFunc_SelectFloat_ReturnValue: float, CallFunc_MakeVector_ReturnValue: FVector, CallFunc_MakeVector_ReturnValue_1: FVector, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_Add_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_SphereTraceSingle_OutHit: FHitResult, CallFunc_SphereTraceSingle_ReturnValue: bool, CallFunc_BreakHitResult_bBlockingHit: bool, CallFunc_BreakHitResult_bInitialOverlap: bool, CallFunc_BreakHitResult_Time: float, CallFunc_BreakHitResult_Distance: float, CallFunc_BreakHitResult_Location: FVector, CallFunc_BreakHitResult_ImpactPoint: FVector, CallFunc_BreakHitResult_Normal: FVector, CallFunc_BreakHitResult_ImpactNormal: FVector, CallFunc_BreakHitResult_PhysMat: UPhysicalMaterial*, CallFunc_BreakHitResult_HitActor: AActor*, CallFunc_BreakHitResult_HitComponent: UPrimitiveComponent*, CallFunc_BreakHitResult_HitBoneName: FName, CallFunc_BreakHitResult_HitItem: int32, CallFunc_BreakHitResult_FaceIndex: int32, CallFunc_BreakHitResult_TraceStart: FVector, CallFunc_BreakHitResult_TraceEnd: FVector, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_GetDisplayName_ReturnValue_1: FString, CallFunc_Conv_BoolToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_3: FString | void |
| Find Unsaddle Pos | wloc: FVector, wrot: FRotator, trySlim?: bool, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_GetDisplayName_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_K2_GetComponentToWorld_ReturnValue: FTransform, CallFunc_K2_GetComponentToWorld_ReturnValue_1: FTransform, CallFunc_BreakTransform_Location: FVector, CallFunc_BreakTransform_Rotation: FRotator, CallFunc_BreakTransform_Scale: FVector, CallFunc_BreakTransform_Location_1: FVector, CallFunc_BreakTransform_Rotation_1: FRotator, CallFunc_BreakTransform_Scale_1: FVector, CallFunc_GetDisplayName_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_K2_GetComponentToWorld_ReturnValue_2: FTransform, CallFunc_BreakTransform_Location_2: FVector, CallFunc_BreakTransform_Rotation_2: FRotator, CallFunc_BreakTransform_Scale_2: FVector, CallFunc_GetDisplayName_ReturnValue_3: FString, CallFunc_K2_GetComponentToWorld_ReturnValue_3: FTransform, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_BreakTransform_Location_3: FVector, CallFunc_BreakTransform_Rotation_3: FRotator, CallFunc_BreakTransform_Scale_3: FVector, CallFunc_GetDisplayName_ReturnValue_4: FString, CallFunc_K2_GetComponentToWorld_ReturnValue_4: FTransform, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_BreakTransform_Location_4: FVector, CallFunc_BreakTransform_Rotation_4: FRotator, CallFunc_BreakTransform_Scale_4: FVector, CallFunc_isCapsuleFree_free: bool, CallFunc_isCapsuleFree_free_1: bool, CallFunc_isCapsuleFree_free_2: bool, CallFunc_isCapsuleFree_free_3: bool, CallFunc_isCapsuleFree_free_4: bool, CallFunc_isCapsuleFree_free_5: bool, CallFunc_GetDisplayName_ReturnValue_5: FString, CallFunc_Concat_StrStr_ReturnValue_5: FString, CallFunc_K2_GetComponentToWorld_ReturnValue_5: FTransform, CallFunc_BreakTransform_Location_5: FVector, CallFunc_BreakTransform_Rotation_5: FRotator, CallFunc_BreakTransform_Scale_5: FVector, CallFunc_K2_GetComponentToWorld_ReturnValue_6: FTransform, CallFunc_BreakTransform_Location_6: FVector, CallFunc_BreakTransform_Rotation_6: FRotator, CallFunc_BreakTransform_Scale_6: FVector, CallFunc_K2_GetComponentToWorld_ReturnValue_7: FTransform, CallFunc_BreakTransform_Location_7: FVector, CallFunc_BreakTransform_Rotation_7: FRotator, CallFunc_BreakTransform_Scale_7: FVector, CallFunc_K2_GetComponentToWorld_ReturnValue_8: FTransform, CallFunc_BreakTransform_Location_8: FVector, CallFunc_BreakTransform_Rotation_8: FRotator, CallFunc_BreakTransform_Scale_8: FVector, CallFunc_GetOverlappingActors_OverlappingActors: TArray, CallFunc_Array_Length_ReturnValue: int32, CallFunc_GetOverlappingActors_OverlappingActors_1: TArray, CallFunc_GetOverlappingActors_OverlappingActors_2: TArray, CallFunc_Array_Length_ReturnValue_1: int32, CallFunc_Array_Length_ReturnValue_2: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_LessEqual_IntInt_ReturnValue_1: bool, CallFunc_LessEqual_IntInt_ReturnValue_2: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_LessEqual_IntInt_ReturnValue_3: bool, CallFunc_BooleanAND_ReturnValue_1: bool | void |
| OnRep_playerRiding | CallFunc_IsLocallyControlled_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool | void |
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
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_IsActorBeingDestroyed_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, Temp_int_Variable: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue: int32 | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| OnRep_uses? | none | void |
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
| RestartSV | true?: bool | void |
| RestartCl | true?: bool | void |

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
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_GetController_ReturnValue: AController*, CallFunc_Conv_FloatToString_ReturnValue: FString, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_HasAuthority_ReturnValue: bool | void |
| OnRep_destroyed | none | void |
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
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_HasAuthority_ReturnValue: bool | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
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
| getPaintingValue | easel: ACanvasEasel_C*, preventPaint: bool, paintingName: FText, paintingDescr: FText, value: int32, traceOffset: FVector | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_IsActorBeingDestroyed_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool | void |
| EmpStart | duration: float, true: bool | void |
| OnRep_emp? | none | void |
| OnRep_HpRepl | CallFunc_IsValid_ReturnValue: bool, CallFunc_Divide_FloatFloat_ReturnValue: float, CallFunc_Multiply_FloatFloat_ReturnValue: float, CallFunc_FTrunc_ReturnValue: int32, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Conv_StringToText_ReturnValue: FText | void |
| OnRep_foundTarget? | none | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, Temp_int_Variable: int32, CallFunc_FMax_ReturnValue: float, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FMin_ReturnValue: float, CallFunc_GreaterEqual_FloatFloat_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue_1: float, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
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
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText | void |
| OnRep_absoluteLoc | CallFunc_K2_SetActorLocation_SweepHitResult: FHitResult, CallFunc_K2_SetActorLocation_ReturnValue: bool | void |
| OnRep_AttachedToComp | CallFunc_IsValid_ReturnValue: bool, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString | void |
| OnRep_RelativeAttachLoc | CallFunc_Conv_VectorToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString | void |
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
| getPaintingValue | easel: ACanvasEasel_C*, preventPaint: bool, paintingName: FText, paintingDescr: FText, value: int32, traceOffset: FVector, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Greater_IntInt_ReturnValue: bool | void |
| GetRadiation | loc: FVector, power: float | void |
| Taser | secs: float, true: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, wepID: uint8, realDMG: float, K2Node_DynamicCast_AsCharacter: ACharacter*, K2Node_DynamicCast_bSuccess: bool, K2Node_DynamicCast_AsCharacter_1: ACharacter*, K2Node_DynamicCast_bSuccess_1: bool, K2Node_DynamicCast_AsPolice_Dog: APolice_Dog_C*, K2Node_DynamicCast_bSuccess_2: bool, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess_3: bool, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess_4: bool, K2Node_DynamicCast_AsPolice_Dog_1: APolice_Dog_C*, K2Node_DynamicCast_bSuccess_5: bool, K2Node_DynamicCast_AsPlayer_Char_1: APlayerChar_C*, K2Node_DynamicCast_bSuccess_6: bool, K2Node_DynamicCast_AsPlayer_Char_2: APlayerChar_C*, K2Node_DynamicCast_bSuccess_7: bool, CallFunc_GetController_ReturnValue: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess_8: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue_1: int32, CallFunc_Not_PreBool_ReturnValue: bool, K2Node_DynamicCast_AsRemote_Turret: ARemoteTurret_C*, K2Node_DynamicCast_bSuccess_9: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_GetOwner_ReturnValue: AActor*, K2Node_DynamicCast_AsPlayer_Char_3: APlayerChar_C*, K2Node_DynamicCast_bSuccess_10: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, K2Node_DynamicCast_AsPlayer_AI: APlayerAI_C*, K2Node_DynamicCast_bSuccess_11: bool, CallFunc_Add_IntInt_ReturnValue_2: int32, K2Node_DynamicCast_AsPlayer_Char_4: APlayerChar_C*, K2Node_DynamicCast_bSuccess_12: bool, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, Temp_int_Variable: int32, Temp_int_Variable_1: int32, Temp_int_Variable_2: int32, CallFunc_GreaterEqual_IntInt_ReturnValue: bool, Temp_int_Variable_3: int32, CallFunc_GreaterEqual_IntInt_ReturnValue_1: bool, CallFunc_HasAuthority_ReturnValue: bool, K2Node_DynamicCast_AsPlayer_Char_5: APlayerChar_C*, K2Node_DynamicCast_bSuccess_13: bool, CallFunc_NotEqual_BoolBool_ReturnValue: bool, CallFunc_GetGameState_ReturnValue: AGameStateBase*, CallFunc_GetAllActorsOfClass_OutActors: TArray, K2Node_DynamicCast_AsHeist_GS: AHeistGS_C*, K2Node_DynamicCast_bSuccess_14: bool, CallFunc_RandomArray_randomAct: AActor*, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, CallFunc_K2_SetActorLocation_SweepHitResult: FHitResult, CallFunc_K2_SetActorLocation_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_GetPlayersInEachTeam_robbers: int32, CallFunc_GetPlayersInEachTeam_cops: int32, CallFunc_GetGameState_ReturnValue_1: AGameStateBase*, CallFunc_EqualEqual_IntInt_ReturnValue: bool, K2Node_DynamicCast_AsHeist_GS_1: AHeistGS_C*, K2Node_DynamicCast_bSuccess_15: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool, K2Node_DynamicCast_AsPlayer_Char_6: APlayerChar_C*, K2Node_DynamicCast_bSuccess_16: bool, CallFunc_GetController_ReturnValue_1: AController*, K2Node_DynamicCast_AsHeist_PC_1: AHeistPC_C*, K2Node_DynamicCast_bSuccess_17: bool, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue_3: int32, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_GetAllActorsOfClass_OutActors_1: TArray, CallFunc_Array_Get_Item: APlayerStart*, CallFunc_K2_GetActorLocation_ReturnValue_2: FVector, CallFunc_K2_SetActorLocation_SweepHitResult_1: FHitResult, CallFunc_K2_SetActorLocation_ReturnValue_1: bool, CallFunc_GetGameMode_ReturnValue: AGameModeBase*, K2Node_DynamicCast_AsHeist_GM: AHeistGM_C*, K2Node_DynamicCast_bSuccess_18: bool, CallFunc_GetAlivePlayers_CopsAlive: TArray, CallFunc_GetAlivePlayers_CopsNum: int32, CallFunc_GetAlivePlayers_RobsAlive: TArray, CallFunc_GetAlivePlayers_RobsNum: int32, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue_1: FString, K2Node_DynamicCast_AsPlayer_AI_Rob_1: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess_19: bool, CallFunc_Multiply_FloatFloat_ReturnValue: float, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_GetGameMode_ReturnValue_1: AGameModeBase*, CallFunc_VSize_ReturnValue: float, K2Node_DynamicCast_AsHeist_GM_1: AHeistGM_C*, K2Node_DynamicCast_bSuccess_20: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_GetPlayersAliveFromEachTeam_CopsAlive: TArray, CallFunc_GetPlayersAliveFromEachTeam_CopsNum: int32, CallFunc_GetPlayersAliveFromEachTeam_RobsAlive: TArray, CallFunc_GetPlayersAliveFromEachTeam_RobsNum: int32, CallFunc_SelectFloat_ReturnValue: float, CallFunc_LessEqual_IntInt_ReturnValue_1: bool, CallFunc_GetGameMode_ReturnValue_2: AGameModeBase*, CallFunc_GetPlayersAliveFromEachTeam_CopsAlive_1: TArray, CallFunc_GetPlayersAliveFromEachTeam_CopsNum_1: int32, CallFunc_GetPlayersAliveFromEachTeam_RobsAlive_1: TArray, CallFunc_GetPlayersAliveFromEachTeam_RobsNum_1: int32, K2Node_DynamicCast_AsHeist_GM_2: AHeistGM_C*, K2Node_DynamicCast_bSuccess_21: bool, CallFunc_LessEqual_IntInt_ReturnValue_2: bool, CallFunc_GetGameMode_ReturnValue_3: AGameModeBase*, K2Node_DynamicCast_AsHeist_GM_3: AHeistGM_C*, K2Node_DynamicCast_bSuccess_22: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_2: bool, K2Node_DynamicCast_AsPlayer_AI_Rob_2: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess_23: bool, K2Node_DynamicCast_AsPlayer_AI_Cop: APlayerAI_Cop_C*, K2Node_DynamicCast_bSuccess_24: bool, K2Node_DynamicCast_AsPlayer_AI_Cop_1: APlayerAI_Cop_C*, K2Node_DynamicCast_bSuccess_25: bool, CallFunc_GetGameState_ReturnValue_2: AGameStateBase*, K2Node_DynamicCast_AsHeist_GS_2: AHeistGS_C*, K2Node_DynamicCast_bSuccess_26: bool, CallFunc_UtcNow_ReturnValue: FDateTime, CallFunc_Greater_IntInt_ReturnValue_1: bool, CallFunc_BooleanOR_ReturnValue: bool, K2Node_MakeStruct_DeathInfo: FDeathInfo__pf1458230002, CallFunc_GetMaterial_ReturnValue: UMaterialInterface*, CallFunc_GetTransform_ReturnValue: FTransform, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_Conv_FloatToString_ReturnValue_1: FString, CallFunc_FinishSpawningActor_ReturnValue: ARagdollSpawn_C*, CallFunc_Multiply_FloatFloat_ReturnValue_1: float, CallFunc_Multiply_FloatFloat_ReturnValue_2: float, CallFunc_Multiply_FloatFloat_ReturnValue_3: float, K2Node_SwitchInteger_CmpSuccess: bool, CallFunc_Conv_FloatToString_ReturnValue_2: FString, CallFunc_Subtract_FloatFloat_ReturnValue: float, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Conv_FloatToString_ReturnValue_3: FString, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_Concat_StrStr_ReturnValue_5: FString, CallFunc_Concat_StrStr_ReturnValue_6: FString | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| helperPrint | InString: FString | void |
| hasLosTo | act: AActor*, los: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, K2Node_MakeArray_Array: TArray, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_LineTraceSingle_OutHit_1: FHitResult, CallFunc_LineTraceSingle_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_1: bool | void |
| OnRep_tasered? | CallFunc_SelectFloat_ReturnValue: float | void |
| CheckOverlappingLadder | Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, CallFunc_MakeHitResult_ReturnValue: FHitResult, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_GetOverlappingActors_OverlappingActors: TArray, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: AActor*, CallFunc_Conv_IntToString_ReturnValue: FString, K2Node_DynamicCast_AsLadder_Act: ALadderAct_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_VSize_ReturnValue: float, CallFunc_VSize_ReturnValue_1: float, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_LessEqual_FloatFloat_ReturnValue_1: bool, CallFunc_K2_GetComponentLocation_ReturnValue_2: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_3: FVector, CallFunc_Array_Length_ReturnValue_1: int32, CallFunc_Less_IntInt_ReturnValue: bool | void |
| OnRep_dead? | CallFunc_Not_PreBool_ReturnValue: bool | void |
| spottedByCop? | spotted?: bool, cops: TArray, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_RandomFloatInRange_ReturnValue: float, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, CallFunc_MakeVector_ReturnValue: FVector, CallFunc_Add_VectorVector_ReturnValue: FVector, CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_Array_Get_Item: ACharacter*, CallFunc_K2_GetActorLocation_ReturnValue_2: FVector, CallFunc_K2_GetActorRotation_ReturnValue: FRotator, CallFunc_FindLookAtRotation_ReturnValue: FRotator, CallFunc_BreakRotator_Roll: float, CallFunc_BreakRotator_Pitch: float, CallFunc_BreakRotator_Yaw: float, CallFunc_BreakRotator_Roll_1: float, CallFunc_BreakRotator_Pitch_1: float, CallFunc_BreakRotator_Yaw_1: float, CallFunc_MakeRotator_ReturnValue: FRotator, CallFunc_MakeRotator_ReturnValue_1: FRotator, CallFunc_K2_GetActorLocation_ReturnValue_3: FVector, CallFunc_EqualEqual_RotatorRotator_ReturnValue: bool, CallFunc_Add_VectorVector_ReturnValue_1: FVector, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, CallFunc_GetDistanceTo_ReturnValue: float, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_GetAllActorsOfClass_OutActors_1: TArray | void |
| OnRep_difficulty | K2Node_DynamicCast_AsPlayer_AI_Cop: APlayerAI_Cop_C*, K2Node_DynamicCast_bSuccess: bool | void |
| getSpottedRobberItem | found?: bool, item: AActor*, inth: int32, CallFunc_GetGameMode_ReturnValue: AGameModeBase*, K2Node_DynamicCast_AsHeist_GM: AHeistGM_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: AActor*, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_IsValid_ReturnValue: bool, CallFunc_RandomIntegerInRange_ReturnValue: int32, CallFunc_Greater_IntInt_ReturnValue: bool | void |
| OnRep_DeathInfo | none | void |
| canPing | ItemToFind: AActor*, blocked: bool, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: APlayerAI_C*, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_Array_Contains_ReturnValue: bool | void |
| CheckCloseDoor | door: AActor*, block?: bool, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: APlayerAI_C*, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_GetOverlappingActors_OverlappingActors: TArray, CallFunc_Array_Contains_ReturnValue: bool | void |
| BlockedBySmoke? | l1: FVector, l2: FVector, blocked: bool, block: bool, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_bool_True_if_break_was_hit_Variable: bool, Temp_int_Array_Index_Variable: int32, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_GetAllActorsWithInterface_OutActors: TArray, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: AActor*, CallFunc_Less_IntInt_ReturnValue: bool, K2Node_DynamicCast_AsSmoke_Vis_Interface: TScriptInterface, K2Node_DynamicCast_bSuccess: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_VisColl_blocked_: bool | void |
| GetName | name: FString, CallFunc_EqualEqual_IntInt_ReturnValue: bool, CallFunc_SelectString_ReturnValue: FString, CallFunc_EqualEqual_IntInt_ReturnValue_1: bool, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_SelectString_ReturnValue_1: FString, CallFunc_SelectString_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString | void |
| GetPlayersAliveFromEachTeam | CopsAlive: TArray, CopsNum: int32, RobsAlive: TArray, RobsNum: int32, aliverobs: TArray, alivecops: TArray, aiCops: TArray, aiRobs: TArray, Temp_int_Array_Index_Variable: int32, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Loop_Counter_Variable_1: int32, CallFunc_Add_IntInt_ReturnValue_1: int32, Temp_int_Array_Index_Variable_1: int32, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Length_ReturnValue_1: int32, CallFunc_Array_Length_ReturnValue_2: int32, CallFunc_Array_Length_ReturnValue_3: int32, CallFunc_Add_IntInt_ReturnValue_2: int32, CallFunc_Add_IntInt_ReturnValue_3: int32, CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_Array_Get_Item: APlayerAI_C*, CallFunc_Array_Length_ReturnValue_4: int32, CallFunc_Array_Add_ReturnValue: int32, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_Array_Add_ReturnValue_1: int32, CallFunc_GetAllActorsOfClass_OutActors_1: TArray, CallFunc_Array_Length_ReturnValue_5: int32, CallFunc_Array_Get_Item_1: APlayerChar_C*, CallFunc_Less_IntInt_ReturnValue_1: bool, CallFunc_Array_AddUnique_ReturnValue: int32, CallFunc_K2_IsValidTimerHandle_ReturnValue: bool, CallFunc_Array_AddUnique_ReturnValue_1: int32, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| OnRep_sprinting? | CallFunc_SelectFloat_ReturnValue: float, CallFunc_IsValid_ReturnValue: bool | void |
| OnRep_shootTarget | CallFunc_IsValid_ReturnValue: bool | void |
| OnRep_ReloadingSV? | none | void |
| AddRecoil | RecoilAdd: float, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FClamp_ReturnValue: float | void |
| OnRep_currentWeaponID | none | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_Add_IntInt_ReturnValue: int32 | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
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
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, Temp_int_Variable: int32, CallFunc_IsValid_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_IsValid_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool | void |
| isSus | isSus?: bool, isSusEasy?: bool, CallFunc_GetOverlappingActors_OverlappingActors: TArray, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_GetMeshZone_zone: TEnumAsByte<ZoneEnum>, CallFunc_GetMeshZone_clothesRow: FName, CallFunc_NotEqual_ByteByte_ReturnValue: bool, CallFunc_NotEqual_ByteByte_ReturnValue_1: bool, CallFunc_VSize_ReturnValue: float, CallFunc_Greater_IntInt_ReturnValue_1: bool, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanOR_ReturnValue_1: bool, CallFunc_BooleanOR_ReturnValue_2: bool, CallFunc_BooleanOR_ReturnValue_3: bool, CallFunc_BooleanOR_ReturnValue_4: bool, CallFunc_BooleanOR_ReturnValue_5: bool | void |
| debugPrint | InString: FString | void |
| OnRep_clothingID | CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Conv_StringToName_ReturnValue: FName, CallFunc_GetDataTableRowFromName_OutRow: FClothingStruct__pf1458230002, CallFunc_GetDataTableRowFromName_ReturnValue: bool | void |
| SetMesh | CallFunc_HasAuthority_ReturnValue: bool, CallFunc_RandomIntegerInRange_ReturnValue: int32, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Conv_StringToName_ReturnValue: FName, CallFunc_GetDataTableRowFromName_OutRow: FClothingStruct__pf1458230002, CallFunc_GetDataTableRowFromName_ReturnValue: bool | void |
| copCanSeeHim? | isSpotted?: bool, spotted?: bool, copActs: TArray, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_bool_True_if_break_was_hit_Variable: bool, Temp_int_Array_Index_Variable: int32, CallFunc_Not_PreBool_ReturnValue: bool, Temp_int_Loop_Counter_Variable_1: int32, CallFunc_Add_IntInt_ReturnValue_1: int32, Temp_int_Loop_Counter_Variable_2: int32, CallFunc_Add_IntInt_ReturnValue_2: int32, Temp_int_Array_Index_Variable_1: int32, Temp_int_Array_Index_Variable_2: int32, Temp_int_Loop_Counter_Variable_3: int32, CallFunc_Add_IntInt_ReturnValue_3: int32, Temp_int_Array_Index_Variable_3: int32, CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_Array_Get_Item: APolice_Dog_C*, CallFunc_Array_Add_ReturnValue: int32, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_Array_Get_Item_1: AActor*, CallFunc_Array_Length_ReturnValue_1: int32, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, CallFunc_Less_IntInt_ReturnValue_1: bool, K2Node_MakeArray_Array: TArray, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, CallFunc_GetAllActorsOfClass_OutActors_1: TArray, CallFunc_Array_Get_Item_2: APlayerAI_Cop_C*, CallFunc_Array_Length_ReturnValue_2: int32, CallFunc_Array_Add_ReturnValue_1: int32, CallFunc_Less_IntInt_ReturnValue_2: bool, CallFunc_GetAllActorsOfClass_OutActors_2: TArray, CallFunc_Array_Length_ReturnValue_3: int32, CallFunc_Array_Get_Item_3: APlayerChar_C*, CallFunc_Less_IntInt_ReturnValue_3: bool, CallFunc_Array_Add_ReturnValue_2: int32 | void |
| OnRep_roped? | none | void |
| OnRep_hasBombBag? | none | void |
| OnRep_moneyAmount | CallFunc_Greater_IntInt_ReturnValue: bool | void |
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
| GetAiInteractTraceLocation | offset: FVector | void |
| PlayerAiCanInteract | prevent?: bool | void |
| PlayerAiInteract | playerai: APlayerAI_C*, true: bool, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Add_IntInt_ReturnValue: int32 | void |
| PlayerAiInteractTimer | playerai: APlayerAI_C*, secs: float | void |
| GetAiInteractWorldLoc | worldLoc: FVector | void |
| CopInter? | shouldInter?: bool | void |
| GetItemName | name: FString | void |
| RefreshPhysics | true: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool, CallFunc_GetPlayerPawn_ReturnValue: APawn*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_SelectFloat_ReturnValue: float | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, OldPlayerMat: UMaterialInterface*, OldPlayerMesh: USkeletalMesh*, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_IsActorBeingDestroyed_ReturnValue: bool | void |
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
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_IsActorBeingDestroyed_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool | void |
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
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_isClass__is_: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_Not_PreBool_ReturnValue_3: bool, CallFunc_LessEqual_IntInt_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanAND_ReturnValue_4: bool, CallFunc_EqualEqual_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_5: bool, CallFunc_EqualEqual_IntInt_ReturnValue_1: bool, CallFunc_Conv_IntToByte_ReturnValue: uint8 | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_EqualEqual_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Conv_StringToName_ReturnValue: FName, CallFunc_GetDataTableRowFromName_OutRow: FWeaponTypesStructs__pf3747386746, CallFunc_GetDataTableRowFromName_ReturnValue: bool, CallFunc_EqualEqual_IntInt_ReturnValue_1: bool, CallFunc_Conv_TextToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString | void |
| OnRep_chuteGone? | none | void |
| OnRep_weaponID | none | void |
| SetWepModel | CallFunc_GetUserWidgetObject_ReturnValue: UUserWidget*, CallFunc_GetUserWidgetObject_ReturnValue_1: UUserWidget*, K2Node_DynamicCast_AsWorld_Wep_Icon: UWorldWepIcon_C*, K2Node_DynamicCast_bSuccess: bool, K2Node_DynamicCast_AsWorld_Wep_Icon_1: UWorldWepIcon_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_GetUserWidgetObject_ReturnValue_2: UUserWidget*, K2Node_DynamicCast_AsWorld_Wep_Icon_2: UWorldWepIcon_C*, K2Node_DynamicCast_bSuccess_2: bool | void |
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
| OnRep_alert | none | void |
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
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_IsActorBeingDestroyed_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool | void |
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
| EmpStart | duration: float, true: bool | void |
| OnRep_emp? | none | void |
| OnRep_tasering? | CallFunc_K2_GetComponentLocation_ReturnValue: FVector | void |
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
| GetAiInteractTraceLocation | offset: FVector | void |
| PlayerAiCanInteract | prevent?: bool | void |
| PlayerAiInteract | playerai: APlayerAI_C*, true: bool, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_HasAuthority_ReturnValue: bool | void |
| PlayerAiInteractTimer | playerai: APlayerAI_C*, secs: float | void |
| GetAiInteractWorldLoc | worldLoc: FVector | void |
| CopInter? | shouldInter?: bool | void |
| GetItemName | name: FString | void |
| RefreshPhysics | true: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_canCarryBombs__can_: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, OldPlayerMat: UMaterialInterface*, OldPlayerMesh: USkeletalMesh*, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool | void |
| GetCustomTrace | Hit: FHitResult | void |
| GetCustomPingSettings | Executor: APawn*, Icon: FName, Conditions: TArray | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, Temp_int_Variable: int32, CallFunc_FMax_ReturnValue: float, CallFunc_GreaterEqual_FloatFloat_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_Add_FloatFloat_ReturnValue_1: float, CallFunc_FMin_ReturnValue: float, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| giveRevive? | oldScore: int32, newScore: int32, stepSize: int32, giveRevive?: bool, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_NotEqual_IntInt_ReturnValue: bool, CallFunc_Conv_IntToFloat_ReturnValue: float, CallFunc_Conv_IntToString_ReturnValue_1: FString, CallFunc_Conv_IntToString_ReturnValue_2: FString, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_Conv_IntToString_ReturnValue_3: FString, CallFunc_Conv_IntToFloat_ReturnValue_1: float, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Divide_FloatFloat_ReturnValue: float, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_FCeil_ReturnValue: int32, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Multiply_IntInt_ReturnValue: int32, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_Conv_IntToString_ReturnValue_4: FString, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_GreaterEqual_IntInt_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue_5: FString, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_Conv_IntToString_ReturnValue_5: FString, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue_6: FString, CallFunc_Concat_StrStr_ReturnValue_7: FString, CallFunc_Conv_BoolToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_8: FString, CallFunc_Concat_StrStr_ReturnValue_9: FString, CallFunc_Concat_StrStr_ReturnValue_10: FString, CallFunc_Concat_StrStr_ReturnValue_11: FString, CallFunc_Concat_StrStr_ReturnValue_12: FString | void |
| OnRep_cryptoProgress | CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_IsValid_ReturnValue: bool, CallFunc_SpawnSoundAtLocation_ReturnValue: UAudioComponent*, CallFunc_Less_FloatFloat_ReturnValue: bool | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FClamp_ReturnValue: float | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |

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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_2: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float, CallFunc_Greater_FloatFloat_ReturnValue: bool | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_HasAuthority_ReturnValue: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float | void |
| OnRep_cut | none | void |
| OnRep_destroyed | none | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_Not_PreBool_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, NewLocalVar_0: FTransform | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
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
| EmpStart | duration: float, true: bool | void |
| OnRep_emp? | Temp_bool_Variable: bool, Temp_byte_Variable: TEnumAsByte<ECollisionEnabled::Type>, Temp_byte_Variable_1: TEnumAsByte<ECollisionEnabled::Type>, K2Node_Select_Default: TEnumAsByte<ECollisionEnabled::Type>, CallFunc_Not_PreBool_ReturnValue: bool | void |
| OnRep_hpRepl | CallFunc_MapRangeClamped_ReturnValue: float | void |
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
| getPaintingValue | easel: ACanvasEasel_C*, preventPaint: bool, paintingName: FText, paintingDescr: FText, value: int32, traceOffset: FVector | void |
| InteractAltSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Normal_ReturnValue: FVector, CallFunc_Multiply_VectorInt_ReturnValue: FVector | void |
| TimerAlt | timer: float, retry: bool | void |
| GetAltInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| OnRep_poisoned? | none | void |
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
| getPaintingValue | easel: ACanvasEasel_C*, preventPaint: bool, paintingName: FText, paintingDescr: FText, value: int32, traceOffset: FVector | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_HasAuthority_ReturnValue: bool, CallFunc_GetController_ReturnValue: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| OnRep_improvedSpeed? | CallFunc_SelectFloat_ReturnValue: float, CallFunc_SelectFloat_ReturnValue_1: float | void |
| OnRep_hasWeapons? | none | void |
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
| LosCheck | startLoc: FVector, ignores: TArray, hasLos?: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_Conv_VectorToString_ReturnValue: FString, CallFunc_VSize_ReturnValue: float, CallFunc_VSize_ReturnValue_1: float, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_Conv_FloatToString_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Conv_FloatToString_ReturnValue_2: FString, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Conv_BoolToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Not_PreBool_ReturnValue_3: bool, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanOR_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_SelectString_ReturnValue: FString, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_VSize_ReturnValue: float, CallFunc_VSize_ReturnValue_1: float, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_Not_PreBool_ReturnValue_3: bool, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_4: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_GetController_ReturnValue: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, K2Node_MakeArray_Array: TArray, CallFunc_GetGameMode_ReturnValue: AGameModeBase*, CallFunc_HasAuthority_ReturnValue: bool, K2Node_DynamicCast_AsHeist_GM: AHeistGM_C*, K2Node_DynamicCast_bSuccess_2: bool, CallFunc_ClosestActorOfClass_closest: AActor*, CallFunc_ClosestActorOfClass_dist: float, CallFunc_ClosestActorOfClass_valid: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, K2Node_DynamicCast_AsPlayer_AI_Cop: APlayerAI_Cop_C*, K2Node_DynamicCast_bSuccess_3: bool, CallFunc_LessEqual_FloatFloat_ReturnValue_1: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float, CallFunc_Subtract_FloatFloat_ReturnValue_1: float, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_VSize_ReturnValue: float, CallFunc_VSize_ReturnValue_1: float, CallFunc_Less_FloatFloat_ReturnValue: bool | void |
| OnRep_armorOutside? | none | void |
| OnRep_armorInside? | none | void |
| OnRep_destroyed | none | void |
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
| LosCheck | startLoc: FVector, ignores: TArray, hasLos?: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_Conv_VectorToString_ReturnValue: FString, CallFunc_VSize_ReturnValue: float, CallFunc_VSize_ReturnValue_1: float, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_Conv_FloatToString_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Conv_FloatToString_ReturnValue_2: FString, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Conv_BoolToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Not_PreBool_ReturnValue_3: bool, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanOR_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_SelectString_ReturnValue: FString, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_VSize_ReturnValue: float, CallFunc_VSize_ReturnValue_1: float, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_Not_PreBool_ReturnValue_3: bool, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_4: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_GetController_ReturnValue: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, K2Node_MakeArray_Array: TArray, CallFunc_GetGameMode_ReturnValue: AGameModeBase*, CallFunc_HasAuthority_ReturnValue: bool, K2Node_DynamicCast_AsHeist_GM: AHeistGM_C*, K2Node_DynamicCast_bSuccess_2: bool, CallFunc_ClosestActorOfClass_closest: AActor*, CallFunc_ClosestActorOfClass_dist: float, CallFunc_ClosestActorOfClass_valid: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, K2Node_DynamicCast_AsPlayer_AI_Cop: APlayerAI_Cop_C*, K2Node_DynamicCast_bSuccess_3: bool, CallFunc_LessEqual_FloatFloat_ReturnValue_1: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float, CallFunc_Subtract_FloatFloat_ReturnValue_1: float, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_VSize_ReturnValue: float, CallFunc_VSize_ReturnValue_1: float, CallFunc_Less_FloatFloat_ReturnValue: bool | void |
| OnRep_armorOutside? | none | void |
| OnRep_armorInside? | none | void |
| OnRep_destroyed | none | void |
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
| LosCheck | startLoc: FVector, ignores: TArray, hasLos?: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_Conv_VectorToString_ReturnValue: FString, CallFunc_VSize_ReturnValue: float, CallFunc_VSize_ReturnValue_1: float, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_Conv_FloatToString_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Conv_FloatToString_ReturnValue_2: FString, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue_1: FString, CallFunc_Conv_BoolToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Not_PreBool_ReturnValue_3: bool, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanOR_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_SelectString_ReturnValue: FString, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_2: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_VSize_ReturnValue: float, CallFunc_VSize_ReturnValue_1: float, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_2: bool, CallFunc_Not_PreBool_ReturnValue_3: bool, CallFunc_BooleanAND_ReturnValue_3: bool, CallFunc_BooleanOR_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_4: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Conv_FloatToString_ReturnValue: FString, CallFunc_GetController_ReturnValue: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, K2Node_MakeArray_Array: TArray, CallFunc_GetGameMode_ReturnValue: AGameModeBase*, CallFunc_HasAuthority_ReturnValue: bool, K2Node_DynamicCast_AsHeist_GM: AHeistGM_C*, K2Node_DynamicCast_bSuccess_2: bool, CallFunc_ClosestActorOfClass_closest: AActor*, CallFunc_ClosestActorOfClass_dist: float, CallFunc_ClosestActorOfClass_valid: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, K2Node_DynamicCast_AsPlayer_AI_Cop: APlayerAI_Cop_C*, K2Node_DynamicCast_bSuccess_3: bool, CallFunc_LessEqual_FloatFloat_ReturnValue_1: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float, CallFunc_Subtract_FloatFloat_ReturnValue_1: float, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_K2_GetComponentLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue_1: FVector, CallFunc_VSize_ReturnValue: float, CallFunc_VSize_ReturnValue_1: float, CallFunc_Less_FloatFloat_ReturnValue: bool | void |
| OnRep_armorOutside? | none | void |
| OnRep_armorInside? | none | void |
| OnRep_destroyed | none | void |
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
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, Temp_int_Variable: int32, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_FMax_ReturnValue: float, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FMin_ReturnValue: float, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_GreaterEqual_FloatFloat_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue_1: float, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_IsActorBeingDestroyed_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |

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
| RefreshPhysics | true: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_canCarryBombs__can_: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, OldPlayerMat: UMaterialInterface*, OldPlayerMesh: USkeletalMesh*, CallFunc_canCarryBombs__can_: bool | void |
| help2 | NewParam: bool | void |
| helper | z: TEnumAsByte<ZoneEnum>, c?: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool | void |
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
| getPaintingValue | easel: ACanvasEasel_C*, preventPaint: bool, paintingName: FText, paintingDescr: FText, value: int32, traceOffset: FVector | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_isClass__is_: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_2: bool, Temp_int_Variable: int32, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_Normal_ReturnValue: FVector, CallFunc_Multiply_VectorInt_ReturnValue: FVector | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| Taser | secs: float, true: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, trueDMG: float, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float, CallFunc_GetAnimInstance_ReturnValue: UAnimInstance*, CallFunc_FMax_ReturnValue: float, CallFunc_Greater_FloatFloat_ReturnValue: bool, CallFunc_GetAnimInstance_ReturnValue_1: UAnimInstance*, CallFunc_Montage_IsPlaying_ReturnValue: bool, CallFunc_K2_IsValidTimerHandle_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_Subtract_FloatFloat_ReturnValue_1: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| getRagdollForChar | sniffchar: AActor*, ragdoll: ARagdollSpawn_C*, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_bool_True_if_break_was_hit_Variable: bool, CallFunc_Not_PreBool_ReturnValue: bool, Temp_int_Array_Index_Variable: int32, CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: ARagdollSpawn_C*, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ObjectObject_ReturnValue_1: bool, CallFunc_BooleanOR_ReturnValue: bool | void |
| OnRep_vestHP | CallFunc_Greater_FloatFloat_ReturnValue: bool | void |
| TryStopSniffing | CallFunc_GetAnimInstance_ReturnValue: UAnimInstance*, CallFunc_Montage_IsPlaying_ReturnValue: bool, CallFunc_K2_IsValidTimerHandle_ReturnValue: bool | void |
| OnRep_tasered? | none | void |
| maybeTargetChar | char: ACharacter*, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_GetAnimInstance_ReturnValue: UAnimInstance*, CallFunc_GetAnimInstance_ReturnValue_1: UAnimInstance*, CallFunc_K2_IsValidTimerHandle_ReturnValue: bool, CallFunc_Montage_IsPlaying_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_isClass__is_: bool, CallFunc_IsValid_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_isClass__is_: bool, CallFunc_IsValid_ReturnValue: bool, CallFunc_GetTransform_ReturnValue: FTransform, CallFunc_BreakTransform_Location: FVector, CallFunc_BreakTransform_Rotation: FRotator, CallFunc_BreakTransform_Scale: FVector, CallFunc_Add_VectorVector_ReturnValue: FVector, CallFunc_BreakRotator_Roll: float, CallFunc_BreakRotator_Pitch: float, CallFunc_BreakRotator_Yaw: float, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_MakeRotator_ReturnValue: FRotator, CallFunc_MakeTransform_ReturnValue: FTransform, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_FinishSpawningActor_ReturnValue: APolice_Dog_C* | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| RestartSV | true?: bool | void |
| RestartCl | true?: bool | void |

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
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, Temp_int_Variable: int32, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_FMax_ReturnValue: float, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FMin_ReturnValue: float, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_GreaterEqual_FloatFloat_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue_1: float, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_IsActorBeingDestroyed_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue_1: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, Temp_int_Variable: int32, CallFunc_FMax_ReturnValue: float, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FMin_ReturnValue: float, CallFunc_GreaterEqual_FloatFloat_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue_1: float, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |

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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_Add_IntInt_ReturnValue: int32 | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| OnRep_queen | none | void |
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
| GetAiInteractTraceLocation | offset: FVector | void |
| PlayerAiCanInteract | prevent?: bool | void |
| PlayerAiInteract | playerai: APlayerAI_C*, true: bool, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_HasAuthority_ReturnValue: bool | void |
| PlayerAiInteractTimer | playerai: APlayerAI_C*, secs: float | void |
| GetAiInteractWorldLoc | worldLoc: FVector | void |
| CopInter? | shouldInter?: bool | void |
| GetItemName | name: FString | void |
| RefreshPhysics | true: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, OldPlayerMat: UMaterialInterface*, OldPlayerMesh: USkeletalMesh* | void |
| GetCustomTrace | Hit: FHitResult | void |
| GetCustomPingSettings | Executor: APawn*, Icon: FName, Conditions: TArray | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_GetDistanceTo_ReturnValue: float, CallFunc_IsValid_ReturnValue: bool, CallFunc_Divide_FloatFloat_ReturnValue: float, CallFunc_FTrunc_ReturnValue: int32, K2Node_MakeStruct_FormatArgumentData: FFormatArgumentData, K2Node_MakeArray_Array: TArray, CallFunc_Format_ReturnValue: FText | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_bool_True_if_break_was_hit_Variable: bool, Temp_int_Array_Index_Variable: int32, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_GetComponentsByTag_ReturnValue: TArray, CallFunc_Array_Get_Item: USceneComponent*, CallFunc_IsValid_ReturnValue: bool, CallFunc_K2_GetComponentLocation_ReturnValue: FVector, CallFunc_tpClear__clear: bool, CallFunc_K2_SetActorLocation_SweepHitResult: FHitResult, CallFunc_K2_SetActorLocation_ReturnValue: bool, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool, CallFunc_GetDistanceTo_ReturnValue: float, CallFunc_MapRangeClamped_ReturnValue: float | void |
| OnRep_running? | CallFunc_SelectFloat_ReturnValue: float | void |
| OnRep_finished? | none | void |
| tpClear? | worldPos: FVector, char: ACharacter*, clear: bool, K2Node_MakeArray_Array: TArray, CallFunc_GetScaledCapsuleSize_OutRadius: float, CallFunc_GetScaledCapsuleSize_OutHalfHeight: float, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_CapsuleTraceSingle_OutHit: FHitResult, CallFunc_CapsuleTraceSingle_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool | void |
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
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue: FString, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, K2Node_DynamicCast_AsPlayer_AI_Rob: APlayerAI_Rob_C*, K2Node_DynamicCast_bSuccess_1: bool, CallFunc_GetGameTimeSinceCreation_ReturnValue: float, CallFunc_Subtract_FloatFloat_ReturnValue: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| getOverlappingFriendlies | ignore: AActor*, near: bool, friendlyNearby: bool, Temp_bool_True_if_break_was_hit_Variable: bool, Temp_int_Array_Index_Variable: int32, CallFunc_Not_PreBool_ReturnValue: bool, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_bool_True_if_break_was_hit_Variable_1: bool, Temp_int_Array_Index_Variable_1: int32, CallFunc_Not_PreBool_ReturnValue_1: bool, Temp_int_Loop_Counter_Variable_1: int32, CallFunc_Add_IntInt_ReturnValue_1: int32, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: UClass*, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_GetOverlappingActors_OverlappingActors: TArray, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Array_Get_Item_1: AActor*, CallFunc_NotEqual_ObjectObject_ReturnValue: bool, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Array_Length_ReturnValue_1: int32, CallFunc_Less_IntInt_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_1: bool | void |
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
| OnRep_canvasWorld | none | void |
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
| GetAltInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, CallFunc_MakeLiteralText_ReturnValue: FText, CallFunc_isClass_is: bool, CallFunc_Conv_TextToString_ReturnValue: FString, CallFunc_Conv_StringToText_ReturnValue: FText, CallFunc_Less_FloatFloat_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue_1: bool | void |
| InteractAltSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_GreaterEqual_FloatFloat_ReturnValue: bool, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_Divide_FloatFloat_ReturnValue: float, CallFunc_SelectFloat_ReturnValue: float, CallFunc_Multiply_IntFloat_ReturnValue: float, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_FTrunc_ReturnValue: int32, CallFunc_FClamp_ReturnValue: float, CallFunc_Add_IntInt_ReturnValue: int32 | void |
| TimerAlt | timer: float, retry: bool | void |
| OnRep_painter | none | void |
| addUniquePaintingToStats | placedPaintings: TArray, Temp_int_Array_Index_Variable: int32, CallFunc_Conv_IntToString_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_1: FString, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable_1: int32, Temp_int_Loop_Counter_Variable_1: int32, CallFunc_Conv_IntToString_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue_2: FString, CallFunc_Add_IntInt_ReturnValue_1: int32, CallFunc_Concat_StrStr_ReturnValue_3: FString, CallFunc_Array_Get_Item: FString, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Concat_StrStr_ReturnValue_4: FString, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_GetPlayerController_ReturnValue: APlayerController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool, CallFunc_Array_Length_ReturnValue_1: int32, CallFunc_IsLocalController_ReturnValue: bool, CallFunc_GreaterEqual_IntInt_ReturnValue: bool, CallFunc_Conv_TextToString_ReturnValue: FString, CallFunc_Array_Get_Item_1: FString, CallFunc_IsEmpty_ReturnValue: bool, CallFunc_Concat_StrStr_ReturnValue_5: FString, CallFunc_Array_Get_Item_2: FString, CallFunc_Array_Length_ReturnValue_2: int32, CallFunc_Array_Length_ReturnValue_3: int32, CallFunc_Less_IntInt_ReturnValue_1: bool, CallFunc_Conv_IntToString_ReturnValue_2: FString, CallFunc_Concat_StrStr_ReturnValue_6: FString, CallFunc_Array_Length_ReturnValue_4: int32, CallFunc_Concat_StrStr_ReturnValue_7: FString, CallFunc_Conv_IntToString_ReturnValue_3: FString, CallFunc_JoinStringArray_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue_8: FString, CallFunc_Concat_StrStr_ReturnValue_9: FString, CallFunc_Concat_StrStr_ReturnValue_10: FString, CallFunc_Concat_StrStr_ReturnValue_11: FString, CallFunc_Concat_StrStr_ReturnValue_12: FString, CallFunc_Concat_StrStr_ReturnValue_13: FString, CallFunc_Concat_StrStr_ReturnValue_14: FString, CallFunc_GetCustomConfigVar_String_IsValid: bool, CallFunc_GetCustomConfigVar_String_ReturnValue: FString, CallFunc_Conv_TextToString_ReturnValue_1: FString, CallFunc_Concat_StrStr_ReturnValue_15: FString, CallFunc_Concat_StrStr_ReturnValue_16: FString, CallFunc_Concat_StrStr_ReturnValue_17: FString, CallFunc_Array_Add_ReturnValue: int32, CallFunc_Array_Contains_ReturnValue: bool, CallFunc_ParseIntoArray_ReturnValue: TArray, CallFunc_IsLocallyControlled_ReturnValue: bool, CallFunc_IsValid_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| OnRep_paintingName | CallFunc_GetUserWidgetObject_ReturnValue: UUserWidget*, CallFunc_IsValid_ReturnValue: bool, K2Node_DynamicCast_AsPainting_Name_UI: UPaintingNameUI_C*, K2Node_DynamicCast_bSuccess: bool | void |
| OnRep_falling? | CallFunc_HasAuthority_ReturnValue: bool | void |
| OnRep_ProgressSV | none | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| OnRep_active? | CallFunc_IsValid_ReturnValue: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_SpawnSoundAtLocation_ReturnValue: UAudioComponent* | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, Temp_int_Variable: int32, CallFunc_FMax_ReturnValue: float, CallFunc_GreaterEqual_FloatFloat_ReturnValue: bool, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_Add_FloatFloat_ReturnValue_1: float, CallFunc_FMin_ReturnValue: float, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| OnRep_remainingBalls | Temp_int_Variable: int32, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue: int32, CallFunc_Subtract_IntInt_ReturnValue: int32, CallFunc_Array_Get_Item: USceneComponent*, CallFunc_Array_IsValidIndex_ReturnValue: bool | void |
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
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_isClass_is: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, K2Node_MakeStruct_FormatArgumentData: FFormatArgumentData, K2Node_MakeArray_Array: TArray, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Format_ReturnValue: FText | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_isClass_is: bool, CallFunc_BooleanAND_ReturnValue: bool | void |
| OnRep_destroyed? | Temp_bool_Variable: bool, Temp_byte_Variable: TEnumAsByte<ECollisionEnabled::Type>, Temp_byte_Variable_1: TEnumAsByte<ECollisionEnabled::Type>, CallFunc_GetTransform_ReturnValue: FTransform, CallFunc_K2_AttachToComponent_ReturnValue: bool, CallFunc_TransformLocation_ReturnValue: FVector, CallFunc_TransformRotation_ReturnValue: FRotator, CallFunc_K2_SetWorldLocationAndRotation_SweepHitResult: FHitResult, K2Node_Select_Default: TEnumAsByte<ECollisionEnabled::Type>, CallFunc_SelectFloat_ReturnValue: float | void |
| customDestroyedHandling | handled?: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_Add_VectorVector_ReturnValue: FVector, CallFunc_MakeTransform_ReturnValue: FTransform, CallFunc_BeginDeferredActorSpawnFromClass_ReturnValue: AActor*, CallFunc_FinishSpawningActor_ReturnValue: AScrapSentry_C*, CallFunc_GetController_ReturnValue: AController*, K2Node_DynamicCast_AsHeist_PC: AHeistPC_C*, K2Node_DynamicCast_bSuccess: bool | void |
| UserConstructionScript | CallFunc_Conv_LinearColorToColor_ReturnValue: FColor, CallFunc_IsDedicatedServer_ReturnValue: bool, CallFunc_CreateDynamicMaterialInstance_ReturnValue: UMaterialInstanceDynamic*, CallFunc_IsValid_ReturnValue: bool | void |
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
| EmpStart | duration: float, true: bool, CallFunc_HasAuthority_ReturnValue: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| OnRep_walkSpeedSlow? | CallFunc_SelectFloat_ReturnValue: float | void |
| OnRep_firing? | CallFunc_SelectFloat_ReturnValue: float | void |
| findClosestBurning | plant: AActor*, otherTargets: TMap, barrels: TArray, bombs: TArray, closestP: AIgniteablePlant_C*, closestD: float, Temp_int_Array_Index_Variable: int32, Temp_bool_True_if_break_was_hit_Variable: bool, CallFunc_Not_PreBool_ReturnValue: bool, CallFunc_Array_Length_ReturnValue: int32, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable_1: int32, Temp_int_Loop_Counter_Variable_1: int32, CallFunc_Add_IntInt_ReturnValue_1: int32, Temp_int_Loop_Counter_Variable_2: int32, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue_2: int32, Temp_bool_True_if_break_was_hit_Variable_1: bool, CallFunc_Not_PreBool_ReturnValue_1: bool, Temp_int_Array_Index_Variable_2: int32, CallFunc_BooleanAND_ReturnValue: bool, CallFunc_Array_Get_Item: ABoomBarrell_C*, CallFunc_GetOwner_ReturnValue: AActor*, K2Node_DynamicCast_AsPlayer_Char: APlayerChar_C*, K2Node_DynamicCast_bSuccess: bool, Temp_int_Loop_Counter_Variable_3: int32, CallFunc_Add_IntInt_ReturnValue_3: int32, Temp_int_Array_Index_Variable_3: int32, CallFunc_Array_Get_Item_1: AMadmanBomb_C*, CallFunc_Map_Find_Value: int32, CallFunc_Map_Find_ReturnValue: bool, CallFunc_Greater_IntInt_ReturnValue: bool, CallFunc_Array_Length_ReturnValue_1: int32, CallFunc_Less_IntInt_ReturnValue_1: bool, CallFunc_BooleanAND_ReturnValue_1: bool, CallFunc_Map_Find_Value_1: int32, CallFunc_Map_Find_ReturnValue_1: bool, CallFunc_Greater_IntInt_ReturnValue_1: bool, CallFunc_Map_Find_Value_2: int32, CallFunc_Map_Find_ReturnValue_2: bool, CallFunc_LessEqual_IntInt_ReturnValue: bool, CallFunc_Map_Find_Value_3: int32, CallFunc_Map_Find_ReturnValue_3: bool, CallFunc_LessEqual_IntInt_ReturnValue_1: bool, CallFunc_MakeLiteralInt_ReturnValue: int32, CallFunc_GetAllActorsOfClass_OutActors: TArray, CallFunc_Array_Get_Item_2: ASweepo_C*, CallFunc_Array_Length_ReturnValue_2: int32, CallFunc_Less_IntInt_ReturnValue_2: bool, CallFunc_Map_Find_Value_4: int32, CallFunc_Map_Find_ReturnValue_4: bool, CallFunc_NotEqual_ObjectObject_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue_4: int32, CallFunc_GetAllActorsOfClass_OutActors_1: TArray, CallFunc_GetAllActorsOfClass_OutActors_2: TArray, CallFunc_IsValid_ReturnValue: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_BreakVector_X: float, CallFunc_BreakVector_Y: float, CallFunc_BreakVector_Z: float, CallFunc_Array_Length_ReturnValue_3: int32, CallFunc_Array_Get_Item_3: AIgniteablePlant_C*, CallFunc_Less_IntInt_ReturnValue_3: bool, CallFunc_Map_Find_Value_5: int32, CallFunc_Map_Find_ReturnValue_5: bool, CallFunc_Greater_IntInt_ReturnValue_2: bool, CallFunc_Map_Find_Value_6: int32, CallFunc_Map_Find_ReturnValue_6: bool, CallFunc_LessEqual_IntInt_ReturnValue_2: bool, CallFunc_GetDistanceTo_ReturnValue: float, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, CallFunc_BreakVector_X_1: float, CallFunc_BreakVector_Y_1: float, CallFunc_BreakVector_Z_1: float, CallFunc_NearlyEqual_FloatFloat_ReturnValue: bool, CallFunc_SelectFloat_ReturnValue: float, CallFunc_Add_FloatFloat_ReturnValue: float, CallFunc_Greater_FloatFloat_ReturnValue: bool | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_GetOwner_ReturnValue: AActor*, CallFunc_EqualEqual_ObjectObject_ReturnValue: bool, CallFunc_EqualEqual_ByteByte_ReturnValue: bool, CallFunc_IsActorBeingDestroyed_ReturnValue: bool, CallFunc_Add_IntInt_ReturnValue: int32 | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| EmpStart | duration: float, true: bool | void |
| OnRep_shooting? | CallFunc_HasAuthority_ReturnValue: bool, CallFunc_K2_IsValidTimerHandle_ReturnValue: bool | void |
| OnRep_emp? | CallFunc_Not_PreBool_ReturnValue: bool | void |
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
| EmpStart | duration: float, true: bool, CallFunc_HasAuthority_ReturnValue: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_Subtract_FloatFloat_ReturnValue: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| findBlockInDir | dirWorld: FVector, limit: FVector, Temp_object_Variable: TArray, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, CallFunc_BreakHitResult_bBlockingHit: bool, CallFunc_BreakHitResult_bInitialOverlap: bool, CallFunc_BreakHitResult_Time: float, CallFunc_BreakHitResult_Distance: float, CallFunc_BreakHitResult_Location: FVector, CallFunc_BreakHitResult_ImpactPoint: FVector, CallFunc_BreakHitResult_Normal: FVector, CallFunc_BreakHitResult_ImpactNormal: FVector, CallFunc_BreakHitResult_PhysMat: UPhysicalMaterial*, CallFunc_BreakHitResult_HitActor: AActor*, CallFunc_BreakHitResult_HitComponent: UPrimitiveComponent*, CallFunc_BreakHitResult_HitBoneName: FName, CallFunc_BreakHitResult_HitItem: int32, CallFunc_BreakHitResult_FaceIndex: int32, CallFunc_BreakHitResult_TraceStart: FVector, CallFunc_BreakHitResult_TraceEnd: FVector | void |
| calcBounceDir | incVel: FVector, impactNormal: FVector, exitDir: FVector, CallFunc_Dot_VectorVector_ReturnValue: float, CallFunc_Multiply_FloatFloat_ReturnValue: float, CallFunc_Multiply_VectorFloat_ReturnValue: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector | void |
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
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
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
| isSus | isSus?: bool, isSusEasy?: bool, CallFunc_Not_PreBool_ReturnValue: bool | void |
| DealDmg | Damage: float, Source: AActor*, LocLocal: FVector, LocWorld: FVector, DmgType: TEnumAsByte<DamageType>, dontKill?: bool, dead: bool, CallFunc_LessEqual_FloatFloat_ReturnValue: bool, CallFunc_HasAuthority_ReturnValue: bool, CallFunc_GetGameTimeSinceCreation_ReturnValue: float, CallFunc_Subtract_FloatFloat_ReturnValue: float, CallFunc_LessEqual_FloatFloat_ReturnValue_1: bool, CallFunc_Subtract_FloatFloat_ReturnValue_1: float | void |
| bulletsCanDmg? | helper: bool, blockdmg?: bool | void |
| CanBePenetrated? | inputDmg: float, can?: bool, damagePercent: float | void |
| OnRep_hiddenInside? | CallFunc_SpawnSoundAttached_ReturnValue: UAudioComponent*, CallFunc_NotEqual_BoolBool_ReturnValue: bool | void |
| OnRep_frozenMovementSpeed | CallFunc_SelectFloat_ReturnValue: float, CallFunc_SelectFloat_ReturnValue_1: float, CallFunc_MakeRotator_ReturnValue: FRotator | void |
| hasLosTo | otherAct: AActor*, los: bool, K2Node_MakeArray_Array: TArray, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, CallFunc_Add_VectorVector_ReturnValue: FVector, CallFunc_Add_VectorVector_ReturnValue_1: FVector, CallFunc_LineTraceSingle_OutHit: FHitResult, CallFunc_LineTraceSingle_ReturnValue: bool, K2Node_MakeArray_Array_1: TArray, CallFunc_K2_GetActorLocation_ReturnValue_2: FVector, CallFunc_K2_GetActorLocation_ReturnValue_3: FVector, CallFunc_Add_VectorVector_ReturnValue_2: FVector, K2Node_MakeArray_Array_2: TArray, CallFunc_LineTraceSingle_OutHit_1: FHitResult, CallFunc_LineTraceSingle_ReturnValue_1: bool, CallFunc_K2_GetActorLocation_ReturnValue_4: FVector, CallFunc_K2_GetActorLocation_ReturnValue_5: FVector, CallFunc_LineTraceSingle_OutHit_2: FHitResult, CallFunc_LineTraceSingle_ReturnValue_2: bool | void |
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
| InteractAltSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_BreakVector_X: float, CallFunc_BreakVector_Y: float, CallFunc_BreakVector_Z: float, CallFunc_MakeVector_ReturnValue: FVector, CallFunc_Normal_ReturnValue: FVector, CallFunc_Multiply_VectorFloat_ReturnValue: FVector | void |
| TimerAlt | timer: float, retry: bool | void |
| GetAltInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_K2_GetActorLocation_ReturnValue: FVector, CallFunc_K2_GetActorLocation_ReturnValue_1: FVector, CallFunc_Subtract_VectorVector_ReturnValue: FVector, CallFunc_BreakVector_X: float, CallFunc_BreakVector_Y: float, CallFunc_BreakVector_Z: float, CallFunc_MakeVector_ReturnValue: FVector, CallFunc_Normal_ReturnValue: FVector | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText | void |
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
| GetInteractName | PlayerChar: APlayerChar_C*, Name: FString, canInteract?: bool, transName: FText, deniedName: FText, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_Concat_StrStr_ReturnValue: FString, CallFunc_getHeistGS_gs: AHeistGS_C*, CallFunc_getHeistGS_gs_1: AHeistGS_C* | void |
| InteractSV | PlayerChar: APlayerChar_C*, true: bool, CallFunc_GetDisplayName_ReturnValue: FString, CallFunc_getHeistGS_gs: AHeistGS_C*, CallFunc_Concat_StrStr_ReturnValue: FString | void |
| InteractTimer | playerchar: APlayerChar_C*, timer: float, retry: bool | void |
| ignoreDistanceChecks | ignore?: bool | void |
| GetModMeshComponent | ComponentName: FString, Object: UActorComponent*, CallFunc_Map_Find_Value: USceneComponent*, CallFunc_Map_Find_ReturnValue: bool | void |
| GetLocalVar | Key: FString, Value: FString, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: FF_SavedVar__pf523916617, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_EqualEqual_StrStr_ReturnValue: bool | void |
| SetLocalVar | Key: FString, Value: FString, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, K2Node_MakeStruct_F_SavedVar: FF_SavedVar__pf523916617, CallFunc_Array_Add_ReturnValue: int32, K2Node_MakeStruct_F_SavedVar_1: FF_SavedVar__pf523916617, CallFunc_Array_Get_Item: FF_SavedVar__pf523916617, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_EqualEqual_StrStr_ReturnValue: bool | void |
| GetReplicatedVar | Key: FString, Value: FString, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Array_Get_Item: FF_SavedVar__pf523916617, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_EqualEqual_StrStr_ReturnValue: bool | void |
| SetReplicatedVar | Key: FString, Value: FString, Temp_int_Loop_Counter_Variable: int32, CallFunc_Add_IntInt_ReturnValue: int32, Temp_int_Array_Index_Variable: int32, K2Node_MakeStruct_F_SavedVar: FF_SavedVar__pf523916617, CallFunc_Array_Add_ReturnValue: int32, K2Node_MakeStruct_F_SavedVar_1: FF_SavedVar__pf523916617, CallFunc_Array_Get_Item: FF_SavedVar__pf523916617, CallFunc_Array_Length_ReturnValue: int32, CallFunc_Less_IntInt_ReturnValue: bool, CallFunc_EqualEqual_StrStr_ReturnValue: bool | void |
| GetLuaFileName | FileName: FString | void |
| CheckStartScript | none | void |
| AddModMeshComponent | ComponentName: FString, MeshFileName: FString, TextureFileName: FString | void |
| LuaTick | none | void |

---

