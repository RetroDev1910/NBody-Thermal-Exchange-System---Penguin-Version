# NBody-Thermal-Exchange-System - Penguin Version

A Linux Version of wmc23nhj09's software

A program written in C++ using SDL3 that shows the laws of thermodynamics, showing exchange between objects via conduction and radiation. 

## OVERVIEW

This project simulates how objects in deep space radiate their heat to space and other objects via conduction when touching and radiation when apart.
This project includes blackbody radiation colour mapping to simulate how an object would look at specific temperatures.

## CONTROLS

Q - Change Mode
E - Destroy Mode

Green - Create Mode
Blue - Move Mode
Red - Destroy Mode

## CURRENT FEATURES

* Blackbody radiation colour mapping
* Temperature loss to deep space using Stefan-Boltzmann's law
* Temperature Equilibrium between objects at a distance due to radiation
* Obey Conservation of energy at a distance
* Draggable objects
* Changeable mass and physics states of objects
* Spawnable objects
* Basic UI system
* Real time 2 way block property comparison

## IN DEVELOPMENT FEATURES

* None As Of Now

## FUTURE FEATURES

* Barnes-Hutt Algorithm
* etc.

## TEST VALIDATIONS
### ADDED
* Stefan-Boltzmann Single Step Deep Space Cooling
  >**NOTE:** As temperature increases, the margin of error increases due to the non-linear `(T^4)` relationship in Stefan-Boltzmann radiation. This test allows up to 1% error for single-step calculations. A future multi-step simulation stability test will verify accuracy using smaller timesteps and improve high-temperature accuracy.

* Energy Conservation of objects finding Equilibrium
  >**NOTE:** Energy conservation managed to achieve a temperature different of 7.5 parts per million during tests (0.000075%)! 

### TO ADD
* Multi-step simulation stability
* Blackbody radiation -> RGB colour mapping validation
* etc.

## REQUIREMENTS

* C++ 17 or newer
* GCC or G++

## BUILD

1. Run this in your terminal
g++ -std=c++17 src/*.cpp Third-Party/*.cpp \
  -Iinclude -IThird-Party \
  -o HeatTransferProjectRED_app \
  $(pkg-config --cflags --libs sdl3)

>**Note:** The SDL3 Development Kit is designed to be reused across multiple SDL3 projects. The project configuration should only require updating the SDL3 paths to match the user's local installation. This repository assumes basic knowledge of Visual Studio C++ project configuration. Users should configure their project include paths and linker settings to point to this development kit.

>**Contingency:** All of this project's own header files are already configured for the ease of building, only the [SDL3 Development Kit](https://github.com/wmc23nhj09/SDL3_Development_Kit)'s files need to be configured (Step 3). If the project's own header files are not able to be found, either add them to the project's local `src` file, or link your relative path under both projects Additional Include Directories configuration settings.

## KNOWN LIMITATIONS

* None As Of Now
