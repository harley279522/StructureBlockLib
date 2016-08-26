# StructureBlockLib

## Description

Simple spigot plugin to modify structureblocks on your minecraft server.

## Features

* NMS Implementation of the StructureBlock.
* StructureApi to save or load structures without a structureblock. 
* Version support 1.9.R1 - 1.10.R1
* Interface Configuration and sending update packets.
* Lightweight

## Installation

* Download the source code and copy it into your own projects.
   OR
* Download the StructureBlockLib.jar and put it into your plugin folder and use it as library in your own projects.

## How to use the it

#### Obtain an existing structureblock

```
Block block = new Location(Bukkit.getWorld("world"), 0,0,0);
StructureBlock structureBlock = StructureBlockApi.from(block);
structureBlock.setStructureMode(StructureMode.SAVE);
```
#### Modify the structureblock
```
StructureBlockSave structureBlockSave = (StructureBlockSave) structureBlock;
StructureBlockLoad structureBlockLoad = (StructureBlockLoad) structureBlock;
StructureBlockData structureBlockData = (StructureBlockData) structureBlock;
StructureBlockCorner structureBlockCorner = (StructureBlockCorner) structureBlock;

structureBlockSave.setSaveName("CustomSaveName");
structureBlockSave.update();
```

#### Store a structure without a structureblock by corner and sizeX, sizeY and sizeZ
```
StructureBlockApi.save("author", "mysavename", new Location(Bukkit.getWorld("world"), 200, 5, 200), new Vector(5,5,5));
```
#### Store a structure without a structureblock by two corners
```
StructureBlockApi.save("author", "mysavename", new Location(Bukkit.getWorld("world"), 195, 5, 195), new Location(Bukkit.getWorld("world"), 200, 10, 200) );
```
#### Load a structure without a structureblock
```
StructureBlockApi.load("author", "mysavename", new Location(Bukkit.getWorld("world"),400, 5, 400));
```

## Lincence

The source code is licensed under the MIT license. 