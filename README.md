<<<<<<< HEAD
This repository contains my SMAPI mods for Stardew Valley. See the individual mods for
documentation and release notes:

* [Chests Anywhere](ChestsAnywhere)
* [Lookup Anything](LookupAnything)
* [Skip Intro](SkipIntro)

## Compiling the mods
Installing stable releases from Nexus Mods is recommended for most users. If you really want to
compile the mod yourself, read on.

These mods use the [crossplatform build config](https://github.com/Pathoschild/Stardew.ModBuildConfig#readme)
so they can be built on Linux, Mac, and Windows without changes. See [the build config documentation](https://github.com/Pathoschild/Stardew.ModBuildConfig#readme)
for troubleshooting.

### Compiling a mod for testing
To compile a mod and add it to your game's `Mods` directory:

1. Rebuild the project in [Visual Studio](https://www.visualstudio.com/vs/community/) or [MonoDevelop](http://www.monodevelop.com/).  
=======
**Debug Mode** is an open-source [Stardew Valley](http://stardewvalley.net/) mod which lets you
press `~` to view debug information and unlock the game's debug commands (including teleportation
and time manipulation).

Compatible with Stardew Valley 1.1+ on Linux, Mac, and Windows.

## Contents
* [Installation](#installation)
* [Usage](#usage)
* [Configuration](#configuration)
* [Versions](#versions)
* [Compiling the mod](#compiling-the-mod)
* [See also](#see-also)

## Installation
1. [Install the latest version of SMAPI](http://canimod.com/guides/using-mods#installing-smapi).
2. [Install this mod from Nexus mods](http://www.nexusmods.com/stardewvalley/mods/679/).
3. Run the game using SMAPI.

## Usage
Press the `~` key (configurable) to enable or disable debug mode. This will...

1. Show cursor crosshairs (with the current map name and tile position), and the game's built-in debug info:

   ![screenshot](screenshots/debug-mode.png)

2. Unlock the game's built-in debug commands:

   hotkey | action
   :----- | :-----
   `T`    | Add one hour to the clock.
   `SHIFT` + `Y` | Subtract 10 minutes from the clock.
   `Y`    | Add 10 minutes to the clock.
   `1`    | Warp to the mountain (facing Robin's house).
   `2`    | Warp to the town (on the path between the town and community center).
   `3`    | Warp to the farm (at your farmhouse door).
   `4`    | Warp to the forest (near the traveling cart).
   `5`    | Warp to the beach (left of Elliott's house).
   `6`    | Warp to the mine (at the inside entrance).
   `7`    | Warp to the desert (in Sandy's shop).
   `K`    | Move down one mine level. If not currently in the mine, warp to it.
   `F5`   | Toggle the player.
   `F7`   | Draw a tile grid.
   `B`    | Shift the toolbar to show the next higher inventory row.
   `N`    | Shift the toolbar to show the next lower inventory row.

3. If you set `AllowDangerousCommands: true` in the [configuration](#configuration) (disabled by
   default), also unlock these debug commands:

   hotkey | action
   :----- | :-----
   `P`    | Immediately go to bed and start the next day.
   `M`    | Immediately go to bed and start the next season.
   `H`    | Randomise the player's hat.
   `I`    | Randomise the player's hair.
   `J`    | Randomise the player's shirt and pants.
   `L`    | Randomise the player.
   `U`    | Randomise the farmhouse wallpaper and floors.
   `F10`  | **Broken.** Tries to launch a multiplayer server, and crashes.

## Configuration
The mod will work fine out of the box, but you can tweak its settings by editing the `config.json`
file if you want. These are the available settings:

setting           | what it affects
:---------------- | :------------------
`Keyboard`        | Set keyboard bindings. The default values are `~` to toggle debug mode. See [valid keys](https://msdn.microsoft.com/en-us/library/microsoft.xna.framework.input.keys.aspx).
`Controller`      | Set controller bindings. No buttons configured by default. See [valid buttons](https://msdn.microsoft.com/en-us/library/microsoft.xna.framework.input.buttons.aspx).
`AllowDangerousCommands` | Default `false`. This allows debug commands which end the current day/season & save, randomise your player or farmhouse decorations, or crash the game. Only change this if you're aware of the consequences.

## Versions
1.0:
* Initial version which unlocks debug mode.
* Suppressed dangerous options by default.
* Fixed default warp points.

1.1:
* Added active menu name to cursor info.
* Added labels to cursor debug lines.
* Updated to SMAPI 1.3.
* Fixed error when enabled before the game loads.

1.2:
* Fixed `AllowDangerousCommands` option having no effect.

## Compiling the mod
Installing a stable release from Nexus Mods is recommended for most users. If you really want to
compile the mod yourself, read on.

This mod uses the [crossplatform build config](https://github.com/Pathoschild/Stardew.ModBuildConfig#readme)
so it can be built on Linux, Mac, and Windows without changes. See [its documentation](https://github.com/Pathoschild/Stardew.ModBuildConfig#readme)
for troubleshooting.

### Compiling the mod for testing
On Windows:

1. Rebuild the project in [Visual Studio](https://www.visualstudio.com/vs/community/).  
>>>>>>> debugmode/master
   <small>This will compile the code and package it into the mod directory.</small>
2. Launch the project with debugging.  
   <small>This will start the game through SMAPI and attach the Visual Studio debugger.</small>

<<<<<<< HEAD
### Compiling a mod for release
To package a mod for release:

1. Delete the mod's directory in `Mods`.  
   <small>(This ensures the package is clean and has default configuration.)</small>
2. Recompile the mod per the previous section.
3. Launch the game through SMAPI to generate the default `config.json` (if any).
4. Delete the `.cache` in the mod folder.
2. Create a zip file of the mod's folder in the `Mods` folder. The zip name should include the
   mod name and version. For example:

   ```
   LookupAnything-1.0.zip
      LookupAnything/
         LookupAnything.dll
         LookupAnything.pdb
         config.json
         manifest.json
   ```
=======
On Linux or Mac:

1. Rebuild the project in [MonoDevelop](http://www.monodevelop.com/).
2. Copy the following files from the `bin` directory:
   * `manifest.json`
   * `Pathoschild.Stardew.DebugMode.dll`
   * `Pathoschild.Stardew.DebugMode.pdb`
3. Paste the files into a `DebugMode` subdirectory under SMAPI's `Mods` directory.
4. Launch the game through SMAPI.

### Compiling the mod for release
To package the mod for release:

1. Delete the game's `Mods/DebugMode` directory.  
   <small>(This ensures the package will be clean and have default configuration.)</small>
2. Recompile the mod per the previous section.
3. Launch the game through SMAPI to generate the default `config.json`.
2. Create a zip file of the game's `Mods/DebugMode` folder. The zip name should include the
   mod name, version, and platform. For example:

   ```
   DebugMode-1.6-Windows.zip
      DebugMode/
         Pathoschild.Stardew.DebugMode.dll
         Pathoschild.Stardew.DebugMode.pdb
         config.json
         manifest.json
   ```

## See also
* [Nexus mod](http://www.nexusmods.com/stardewvalley/mods/679)
* [Discussion thread](http://www.nexusmods.com/stardewvalley/mods/679)
* My other Stardew Valley mods: [Chests Anywhere](https://github.com/Pathoschild/ChestsAnywhere), [Lookup Anything](https://github.com/Pathoschild/LookupAnything), [No Debug Mode](https://github.com/Pathoschild/Stardew.NoDebugMode), and [Skip Intro](https://github.com/Pathoschild/StardewValley.SkipIntro)
>>>>>>> debugmode/master
