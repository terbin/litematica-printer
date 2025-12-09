# Litematica Printer

> [!WARNING]
> This README is a work in progress and may contain inaccuracies. There are currently no official releases - builds can be obtained from [GitHub Actions](https://github.com/terbin/litematica-printer/actions).

This extension adds printing functionality for [Litematica fabric](https://github.com/maruohon/litematica) 1.21.10. Printer allows players to build big structures more quickly by automatically placing the correct blocks around you.

## Installation

1. Download and install [Fabric](https://fabricmc.net/use/installer/) if you haven't already.
2. Download the latest Litematica Printer release for your Minecraft version from the
   [releases page](https://github.com/terbin/litematica-printer/releases/latest) (The files can be found under
   "assets").
3. Download [Litematica + MaLiLib](https://www.curseforge.com/minecraft/mc-mods/litematica)
   and [Fabric API](https://www.curseforge.com/minecraft/mc-mods/fabric-api/) (≠ Fabric).
4. Place the downloaded .jar files in your `mods/` folder.

[If this is the first fabric mod you are installing, here's an informative video on how to install Fabric mods.](https://www.youtube.com/watch?v=x7gmfib4gHg)

# How To Use

Using the printer is straightforward: You can toggle the feature by pressing `CAPS_LOCK` by default. To configure
variables such as printing speed and range, open Litematica's settings by pressing `M + C` and navigate to "Generic" 
tab. Printer's configuration can be found at the bottom of the page. All printer settings start with the word 'printer'. 
You can also rebind the printing toggle under "Hotkeys" tab. Holding down `V` by default will also print regardless if 
the printer is toggled on or off. All printer settings are designed to work with Grim anticheat out of the box. Some variations for
setting are listed below.

## How to use - Grim bypass setup
This configuration uses a grim bypass to place blocks in the correct orientation and without having to rotate the player.
This setup is recommended as long as it still works.

### Mods
- Install printer for your version.
  Download: https://github.com/terbin/litematica-printer/releases

### Printer Settings
Most important settings:
- Printer range 4.5 - 5
- printerRotatePlayer false
- printerGrimRotate true (may not work on 1.20.4+ clients, if you get lagbag disable and use the settings from the Strict anticheat setup section)
- printerAirPlace true
- For the rest default values should work

## How to use - Grim rotations bypass
This configuration uses a grim bug in combination with ViaFabricPlus to allow for placing blocks without having to rotate 
the player. Blocks placed in this way won't have the correct rotations unless the player rotation is correct.

### Mods
- Install printer for your version.
  Download: https://github.com/terbin/litematica-printer/releases
- You also need ViaFabricPlus if connecting to older server versions

### In Game
- Set ViaFabricPlus to use the target server's version
### Printer Settings
Most important settings:
- Printer range at 4.5 - 4.3
- printerRotatePlayer false
- printerGrimRotate true
- For the rest default values should work

## How to use - Strict anticheat setup

This configuration setup is designed to work as vanilla as possible. If all other bypasses get patched this setup should still work.

### Mods
- Install printer for your version.
  Download: https://github.com/terbin/litematica-printer/releases

### In Game - Printer Settings
Most important settings:
- Set freelook toggle to the same key as printer toggle
- Printer range at 4.5 - 4.3
- printerRotatePlayer true
- printerGrimRotate false
- For the rest default values should work

## Recommended Mapart settings
- printerIgnoreRotations true (this will work for most blocks. But be aware some logs have a different color on maps depending on the rotation.)

### Other features added by this fork:
- Airplace (printerAirPlace). A bit buggy but turning up printerTickDelay makes it more reliable.
- Working inventory management. The default litematica printer has issues with inventory management on servers with Grim anticheat. This fork fixes that.
- autoConvertSchematicToLitematicOnLoad. This setting auto converts schematic files to litematic files when loading them. 
    This is useful when using schematics produced by Rebanes Mapartcraft Website [Rebane's Mapartcraft](https://rebane2001.com/mapartcraft/).
    Without a litematica file baritone won't work with the `#litematica` command

## Issues

This fork is optimized for servers running Grim anticheat. If you have issues
with the printer, **do not** bother the original creator of Litematica (maruohon) with them.

### List of known issues

Currently, the following features are still broken or missing:

- Placing liquids (printing **in** liquids works though)
- Current algorithm for placing rails isn't perfect,
  sometimes it can't place all the rails (to avoid placing anything incorrectly).
- Sometimes rotations on blocks are wrong even with printerIgnoreRotations off
- You might get some ghost items in your inventory
- In rare cases the printer might place the wrong block. This is usually a 1 in about 1000 chance. Can get worse with high ping or unstable connections.

Features that fix existing builds, such as automatic excavation or correcting incorrectly placed blocks, are out of the scope of this mod.

## Credits

This project is a fork of [IceTank's litematica-printer](https://github.com/IceTank/litematica-printer), which itself is a fork of the original [litematica-printer by aleksilassila](https://github.com/aleksilassila/litematica-printer). Thanks to both for their work that made this fork possible.

## Building and Contributing

Intellij is recommended for developing. Just clone the repo and open the project. Make sure to use at least Java JDK 21 or Gradle will complain. The jar file can be built using the build task under
`v1_21_10 > Tasks > build > build`.
