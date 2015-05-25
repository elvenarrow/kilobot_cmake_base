# Using CMake to program Kilobots

This repository contains the base files for compiling C code for Kilobots using CMake. 

###  Preamble

If you don't know what Kilobots are, you can get information here: [http://www.eecs.harvard.edu/ssr/projects/progSA/kilobot.html](http://www.eecs.harvard.edu/ssr/projects/progSA/kilobot.html).

If you don't know what CMake is, you can get information here: [http://www.cmake.org](http://www.cmake.org/)

### 1. Install CMake

***Note:** Linux users can easily install CMake through their distribution's package manager. Mac users can also easily install CMake using the [Homebrew](http://brew.sh/) or [MacPorts](https://www.macports.org/) package managers.* 

Download the CMake installer for your operating system from [http://www.cmake.org/download/](http://www.cmake.org/download/). Follow the instructions included in the installer to proceed with the installation of CMake. 

### 2. Install avr-gcc



### 3. Build Kilolib

[Download Kilolib](https://github.com/acornejo/kilolib/archive/master.zip) and extract the zipped file. 

Using a terminal, navigate to the extracted folder (it should be called `kilolib-master`). Once in the folder, build Kilolib by typing `make` in the terminal. 

### 4. Prepare your project folder

[Download](https://github.com/swarm-lab/kilobot_cmake_base/archive/master.zip) (or fork) this repository. Rename it and place it on your hard drive where you want your project to be located. You can also remove README.md and LICENCE, or replace their content with the appropriate material for your project. 

Copy all files ending in ".h" from the `kilolib-master` folder and paste them in the `include` folder of your project folder. Copy `kilolib.a` from the `kilolib-master/build` folder, paste it in the `lib` folder of your project folder and rename it `libkilolib.a` **(very important)**. 

Open `CMakeLists.txt` in your folder project. 