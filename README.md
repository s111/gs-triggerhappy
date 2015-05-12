# Trigger Happy
Trigger Happy is a game that puts your reaction time to the test.
There is no limit on the amount of players allowed.
The objective is to shoot the boxes that appear on screen as quickly as possible.
The boxes appear for a small amount of time and only the player that first shoots the box gets scored.
The first player to get 15 points wins the game.

## Table of Contents

- [Precompiled](#precompiled)
- [Develop](#develop)
- [Compile and package](#compile-and-package)
- [Screenshots](#screenshots)
	- [Launcher](#launcher)
	- [Controller](#controller)

## Precompiled
The game packaged together with the controller.  
[All Releases](https://github.com/s111/gs-triggerhappy/releases)

Unzip and the ```triggerhappy``` folder can now be added to the game systems ```games``` directory.

## Develop
Download the repository:
```sh
git clone github.com/s111/gs-triggerhappy
```

Import the project into your IDE of choice. Choose a new maven project and import the pom.xml file. For your IDE to be able to compile the games, you first need to have maven generate the native libraries needed by the game. You do this by executing the following command:
```sh
mvn generate-resources
```
Then you need to set VM options to ```-Djava.library.path=target/natives```.

You should now be able to launch the game from your IDE. Remember that you need the game system running in the background for it to work.

## Compile and package
To package the game for distribuiton you must execute the following command:
```sh
mvn clean compile assembly:single
```

Now create this folder structure:  
```sh
triggerhappy/bin
```
Copy ```game.json```, ```screenshots.png``` and the ```controller``` folder into the ```triggerhappy``` folder. Copy the ```target/natives``` folder into it too and rename it to ```lib```. Now copy the jar file in the ```target``` folder into the ```triggerhappy/bin``` folder and rename it to ```triggerhappy.jar```.

You should now have a folder named ```triggerhappy``` which looks something like this:
```
triggerhappy/game.json
triggerhappy/controller/index.html
triggerhappy/controller/controller.js
triggerhappy/bin/triggerhappy.jar
triggerhappy/lib/lwjgl.dll
triggerhappy/lib/...
```
This folder can now be added to the game systems ```games``` directory.

## Screenshots

### Launcher
<img src="https://github.com/s111/gamesystem/blob/master/screenshots/triggerhappy.png" width="640">

### Controller
<img src="https://github.com/s111/gamesystem/blob/master/screenshots/triggerhappy_controller.png" width="320">
