<!-- Auto-generated from JSON by GDScript docs maker. Do not edit this document directly. -->

# Escoria

**Extends:** [Node](../Node)

## Description

The escoria main script

## Enumerations

### GAME\_STATE

```gdscript
const GAME_STATE: Dictionary = {"DEFAULT":0,"DIALOG":1,"WAIT":2}
```

Current game state
* DEFAULT: Common game function
* DIALOG: Game is playing a dialog
* WAIT: Game is waiting

## Constants Descriptions

### BUS\_MASTER

```gdscript
const BUS_MASTER: String = "Master"
```

Audio bus indices.

### BUS\_MUSIC

```gdscript
const BUS_MUSIC: String = "Music"
```

### BUS\_SFX

```gdscript
const BUS_SFX: String = "SFX"
```

### BUS\_SPEECH

```gdscript
const BUS_SPEECH: String = "Speech"
```

### CAMERA\_SCENE\_PATH

```gdscript
const CAMERA_SCENE_PATH: String = "res://addons/escoria-core/game/scenes/camera_player/camera.tscn"
```

## Property Descriptions

### logger

```gdscript
var logger: ESCLogger
```

Logger used

### utils

```gdscript
var utils: ESCUtils
```

Several utilities

### inventory\_manager

```gdscript
var inventory_manager: ESCInventoryManager
```

The inventory manager instance

### action\_manager

```gdscript
var action_manager: ESCActionManager
```

The action manager instance

### esc\_compiler

```gdscript
var esc_compiler: ESCCompiler
```

ESC compiler instance

### event\_manager

```gdscript
var event_manager: ESCEventManager
```

ESC Event manager instance

### globals\_manager

```gdscript
var globals_manager: ESCGlobalsManager
```

ESC globals registry instance

### room\_manager

```gdscript
var room_manager: ESCRoomManager
```

ESC room manager instance

### object\_manager

```gdscript
var object_manager: ESCObjectManager
```

ESC object manager instance

### project\_settings\_manager

```gdscript
var project_settings_manager: ESCProjectSettingsManager
```

ESC project settings manager instance

### command\_registry

```gdscript
var command_registry: ESCCommandRegistry
```

ESC command registry instance

### resource\_cache

```gdscript
var resource_cache: ESCResourceCache
```

Resource cache handler

### room\_terrain

```gdscript
var room_terrain
```

Terrain of the current room

### dialog\_player

```gdscript
var dialog_player: ESCDialogPlayer
```

Dialog player instantiator. This instance is called directly for dialogs.

### inventory

```gdscript
var inventory
```

Inventory scene

### settings

```gdscript
var settings: ESCSaveSettings
```

These are settings that the player can affect and save/load later

### game\_size

```gdscript
var game_size
```

The game resolution

### main

```gdscript
var main
```

The main scene

### current\_state

```gdscript
var current_state
```

The current state of the game

### inputs\_manager

```gdscript
var inputs_manager: ESCInputsManager
```

The escoria inputs manager

### save\_manager

```gdscript
var save_manager: ESCSaveManager
```

Savegames and settings manager

### game\_scene

```gdscript
var game_scene: ESCGame
```

 The game scene loaded

### player\_camera

```gdscript
var player_camera: ESCCamera
```

The main player camera

### start\_script

```gdscript
var start_script: ESCScript
```

The compiled start script loaded from ProjectSettings
escoria/main/game_start_script

## Method Descriptions

### init

```gdscript
func init()
```

Called by Escoria's main_scene as very very first event EVER.
Usually you'll want to show some logos animations before spawning the main
menu in the escoria/main/game_start_script 's :init event

### new\_game

```gdscript
func new_game()
```

Called by Main menu "start new game"

### apply\_settings

```gdscript
func apply_settings(p_settings: ESCSaveSettings) -> void
```

Apply the loaded settings

#### Parameters

* p_settings: Loaded settings

### set\_game\_paused

```gdscript
func set_game_paused(p_paused: bool)
```

Pauses or unpause the game

#### Parameters
- p_paused: if true, pauses the game. If false, unpauses the game.

### run\_event\_from\_script

```gdscript
func run_event_from_script(script: ESCScript, event_name: String)
```

Runs the event "event_name" from the "script" ESC script.

#### Parameters
- script: ESC script containing the event to run. The script must have been
loaded.
- event_name: Name of the event to run

### register\_ui

```gdscript
func register_ui(game_scene: String)
```

Register a user interface. This should be called in a deferred way
from the addon's _enter_tree.

#### Parameters
- game_scene: Path to the game scene extending ESCGame

### deregister\_ui

```gdscript
func deregister_ui(game_scene: String)
```

Deregister a user interface

#### Parameters
- game_scene: Path to the game scene extending ESCGame

### register\_dialog\_manager

```gdscript
func register_dialog_manager(manager_class: String)
```

Register a dialog manager addon. This should be called in a deferred way
from the addon's _enter_tree.

#### Parameters
- manager_class: Path to the manager class script

### deregister\_dialog\_manager

```gdscript
func deregister_dialog_manager(manager_class: String)
```

Deregister a dialog manager addon

#### Parameters
- manager_class: Path to the manager class script

### quit

```gdscript
func quit()
```

Function called to quit the game.

### is\_ready\_for\_inputs

```gdscript
func is_ready_for_inputs() -> bool
```

Used by game.gd to determine whether the game scene is ready to take inputs
from the _input() function. To do so, the current_scene must be set, the game
scene must be set, and the game scene must've been notified that the room
is ready.

*Returns*
true if game scene is ready for inputs

## Signals

- signal paused():  Signal sent when Escoria is paused
- signal resumed(): Signal sent when Escoria is resumed from pause
