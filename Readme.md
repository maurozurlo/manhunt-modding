# Manhunt Modding Cheatsheet

Just a list of stuff that can be modded in MH1 with the respective tools/scripts needed.

## GLOBAL Folder

### /Charpak Folder
> This contains 3d models and textures used when activating certain cheats such as BUNYSUIT, PIGGSUIT.
> More info about dff and txd files below.
 
### /data Folder
> Needs to be unpacked from ManHunt.pak file
> More info soon

### /mpeg Folder
> Videos in bik format for titles / ending of the game.

### /pak Folder
> Models and textures that are common to all levels. Such as rats, crows, etc.
> More info about dff and txd files below.

### /pc_text Folder
> Common text in the game. Info about how to unpack/pack/edit below.
> 
### /sfx
> Particle files.
> More info soon.

### /tvp
> Needs to be unpacked from ManHunt.pak file
> Timed Vector Pairs. Camera angles for executions.

> Structure
- Type (VECPAIR => Regular Vector | VECPAIR@ => Last Vector)
- Duration (How long should the camera stay)
- Camera position X (need negation)
- Camera position Y
- Camera position Z
- Camera look at position X (need negation)
- Camera look at position Y
- Camera look at position Z
- Camera Pan (not 100% sure)
- Camera Roll

### game.scc
> Needs to be unpacked from ManHunt.pak and unpacked 
> with MHT. Contains MLS Code variables which are 
> shared over all levels

### weather.ini
> Needs to be unpacked from ManHunt.pak file
> Contains Weather stuff.

## ManHunt.pak File
> Found in /levels/GLOBAL/data*
> Unmodded game will automatically load its contents instead of .ini files.
> Contains /data and /tvp folders for global.
> Contains one folder per level and inside that it has:
>- entityTypeData.ini
>- levelSetup.ini
>- spl/splines.ini

- 📦 Can be packed/unpacked with [MHT](https://github.com/Sor3nt/manhunt-toolkit/releases)
- 📦 Can be extracted with [PakExtract](https://github.com/ermaccer/pakextract/releases)
- ✅ Can be patched (along other issues) with [pluginMH](https://github.com/ermaccer/Manhunt.PluginMH/releases)
- ✅ Can be patched to load raw files first with [Manhunt PAKPatch](https://github.com/ermaccer/Manhunt.PAKPatch/releases)

##  All Level Files

### /pak folder

#### modelspc.dff
> Contains all 3d models for props and characters in that particular level.
> Should probably not go over 10mb.
- 👁️ Can be previewed using [MHS](https://www.dixmor-hospital.com/mhs/index.php)
- ✏️ Can be edited with any DFF 3D Studio Max script, using the GTA SA option (might need to skip COL). For example, [GF's script based on Kam's](https://gtaforums.com/topic/907323-rel-kams-gta-scripts-2018-upd-31052020/)
- 📦 Can be packed/unpacked with [MHT](https://github.com/Sor3nt/manhunt-toolkit/releases)
- 📦 Can be packed/unpacked visually with [MMCD](https://www.dixmor-hospital.com/mods/view/manhunt-models-compile-decompile)

#### modelspc.txd
> Contains all textures for props and characters in that particular level.
> Textures are always better as powers of 4 (64,128,256,512,1024... etc)
> Textures should be compressed as DXT1. If they have an alpha DXT3 should be used instead.
> Should probably not go over 10mb.
- 👁️ Can be previewed using [MHS](https://www.dixmor-hospital.com/mhs/index.php)
- ✏️ Can be edited with [MagicTXD tool](https://www.gtagarage.com/mods/show.php?id=27862)

#### scene1pc.txd
> Contains all textures for the scene1/2.bsp files.
> Textures are always better as powers of 4 (64,128,256,512,1024... etc)
> Textures should be compressed as DXT1. If they have an alpha DXT3 should be used instead.
> Should probably not go over 10mb.
- 👁️ Can be previewed using [MHS](https://www.dixmor-hospital.com/mhs/index.php)
- ✏️ Can be edited with [MagicTXD tool](https://www.gtagarage.com/mods/show.php?id=27862)

### /pc_text folder

#### pc_{{level name}}_f|g|i|s.gxt
> Contains text for all dialogue in the level.
> Version with no underscore is english.
> f = french
> g = german
> i = italian
> s = spanish
- ✏️ Can be edited (once unpacked) in json format with any text editor (notepad, vscode, vim...)
- 📦 Can be packed/unpacked with [MHT](https://github.com/Sor3nt/manhunt-toolkit/releases)

### /scripts folder

#### {{level name}}.mls
> Contains code for everything that happens in the level.
- 📦 Can be unpacked/compiled with [MHT](https://github.com/Sor3nt/manhunt-toolkit/releases)
- ✏️ Can be edited (once unpacked) in srce format with any text editor (notepad, vscode, vim...)

### /spl folder

#### splines.ini
> Splines loaded for a level are put in here, with setting for the type of spline, and its duration.
> I've no idea.
- ✏️ Can be edited with any text editor (notepad, vscode, vim...)

#### splines.spl
> I've no idea.
- ❌ Can't be edited.

### Root folder

#### allanims.ifp
> Contains all anims for that particular level in blocks.
- ✏️ Can be opened/edited with [Allen's 3D Studio Max script](https://gtaforums.com/topic/745033-3dsmaxrel-manhunt-2-mdl-ifp-importerexporter)
- 📦 Can be packed/unpacked in json format with [MHT](https://github.com/Sor3nt/manhunt-toolkit/releases)

#### {{level name}}.bik / outro.bik
> Found in /levels/{{level name}}
> Prerendered cutscene. Can probably be edited with a bik video tool.

#### collisions.col
> Contains collisions for entities in the level such as the player, hunters, props in the map, etc.
- ✏️ Can be opened/edited with [Allen's 3D Studio Max script](https://gtaforums.com/topic/745033-3dsmaxrel-manhunt-2-mdl-ifp-importerexporter)
- 📦 Can be packed/unpacked in json format with [MHT](https://github.com/Sor3nt/manhunt-toolkit/releases)

#### entity.inst / entity2.inst
> Contains placement/certain values for entities in the level such as the player, hunters, props in the map, etc.
- ✏️ Can be edited visually with [MHS](https://www.dixmor-hospital.com/mhs/index.php)
- ✏️ Can be edited via GUI with [InstEditor](https://github.com/ermaccer/INSTEditor/releases)
- 📦 Can be packed/unpacked in json format with [MHT](https://github.com/Sor3nt/manhunt-toolkit/releases)

#### entityTypeData.ini
> Contains properties for entities in the level such as the player, hunters, props in the map, etc.
- ✏️ Can be edited with any text editor (notepad, vscode, vim...)
- 📦 Can be split/merged back into one file in ini format with [MHT](https://github.com/Sor3nt/manhunt-toolkit/releases)

#### levelSetup.ini
> Contains properties for the world such as the sky color, weather, fog.
- ✏️ Can be edited with any text editor (notepad, vscode, vim...)

#### mapAI.grf
> Contains waypoints for the hunter's AI
- 📦 Can be packed/unpacked in json format with [MHT](https://github.com/Sor3nt/manhunt-toolkit/releases)
- ✏️ Can be edited with any text editor (notepad, vscode, vim...) (once unpacked)

#### picload_pc.txd
> Contains the texture that's seen when this level loads
- 👁️ Can be previewed using [MHS](https://www.dixmor-hospital.com/mhs/index.php)
- ✏️ Can be edited with [MagicTXD tool](https://www.gtagarage.com/mods/show.php?id=27862)

#### picmap.txd / picmmap.txd
> Unused maps.
- 👁️ Can be previewed using [MHS](https://www.dixmor-hospital.com/mhs/index.php)
- ✏️ Can be edited with [MagicTXD tool](https://www.gtagarage.com/mods/show.php?id=27862)

#### scene1.bsp
> Contains geometry data for the level. Every mesh in this file has automatic collision. 
> To avoid players/hunters without ambient light (black) you need to generate PVS
> The default max amount of materials is about 300
> Shadows in the level are controlled by (dark) vertex colors
- ✏️ Can be created using RW SDK 3.5.
- ✏️ PVS can be generated using wrldview from RW SDK 3.5.
- 👁️ Can be previewed using [MHS](https://www.dixmor-hospital.com/mhs/index.php)
- 😈 Max material limit can be disabled with [pluginMH](https://github.com/ermaccer/Manhunt.PluginMH/releases)
- 📹 [Tutorial](https://www.youtube.com/watch?v=eBYBZ3RC2uA)

#### scene2.bsp
> Contains geometry data for the level with no collision. Used for shadows, decals and such.
- ✏️ Can be edited with using RW SDK 3.5
- 📹 [Tutorial](https://www.youtube.com/watch?v=eBYBZ3RC2uA)

#### toc.txt
> The worst file of them all. 
> Unmodded game will gladly crash if any file goes over what's written in this size list of crap. 
- ✏️ Can be edited with any text editor and tears
- 😈 Can be disabled and sent back to hell with [pluginMH](https://github.com/ermaccer/Manhunt.PluginMH/releases)
