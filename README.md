<div align = "center">
<img src=".github/obs-logo.svg" width="128" height="128" />
</div>


## obs-ios-camera-source for linux
### (tested on ubuntu 20.04)

this repository is originally cloned from https://github.com/wtsnz/obs-ios-camera-source
it's only have releases for windows and mac. but this fork https://github.com/dougg3/obs-ios-camera-source have linx support but it's also not bulding in ubuntu 20.04. I made this to compile obs-ios-camera plugin on ubuntu 20.04

### I have to install

    apt install ffmpeg
    apt-get install cmake
    apt-get install g++
    apt-get install libobs0
    apt-get install libobs-dev
    apt-get install libavcodec-dev
    apt install qtbase5-dev

### changes

    Changed 
    external/FindLibObs.cmake

    Add(from https://github.com/Palakis/obs-ndi/blob/ac0a3be1709c18a92a381e480d3ceae5e2dd2b22/external/ObsPluginHelpers.cmake)
    external/ObsPluginHelpers.cmake

### Compile

    mkdir build
    cd build
    cmake .. -DLIBOBS_INCLUDE_DIR=../cmake
    make -j4

After doing this, I manually created the directory structure for the plugin and put it in ~/.config/obs-studio/plugins:

    mkdir -p ~/.config/obs-studio/plugins
    cd ~/.config/obs-studio/plugins
    mkdir -p obs-ios-camera-source/data/locale/
    touch obs-ios-camera-source/data/locale/en-US.ini 
    mkdir -p obs-ios-camera-source/bin/64bit/

    cp build/obs-ios-camera-source.so ~/.config/obs-studio/plugins/obs-ios-camera-source/bin/64bit/
   
==============
Use your iPhone camera as a video source in OBS Studio and stream high quality video from your iPhone's camera over USB.

[![Build status](https://ci.appveyor.com/api/projects/status/ya6xt30mxfnvplna?svg=true)](https://ci.appveyor.com/project/wtsnz/obs-ios-camera-source)
[![Build Status](https://travis-ci.org/wtsnz/obs-ios-camera-source.svg?branch=master)](https://travis-ci.org/wtsnz/obs-ios-camera-source)

To use this you use the [accompanying iOS app](https://will.townsend.io/products/obs-iphone/) to begin streaming in OBS.
