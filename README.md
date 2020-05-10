<div align = "center">
<img src=".github/obs-logo.svg" width="128" height="128" />
</div>


obs-ios-camera-source for linx(tested on ubuntu 20.04)

this repository is originally cloned from https://github.com/wtsnz/obs-ios-camera-source
it's only have releases for windows and mac. but this fork https://github.com/dougg3/obs-ios-camera-source have linx support but it's also not bulding in ubuntu 20.04. I made this to compile obs-ios-camera plugin on ubuntu 20.04

## I have to install

apt-get install cmake
apt-get install g++
apt-get install libobs0
apt-get install libobs-dev
apt install qtbase5-dev

Changed 
external/FindLibObs.cmake

Add(from https://github.com/Palakis/obs-ndi/blob/ac0a3be1709c18a92a381e480d3ceae5e2dd2b22/external/ObsPluginHelpers.cmake)
external/ObsPluginHelpers.cmake

## Compile

cd build
cmake .. -DLIBOBS_INCLUDE_DIR=../cmake
make -j4

==============
Use your iPhone camera as a video source in OBS Studio and stream high quality video from your iPhone's camera over USB.

[![Build status](https://ci.appveyor.com/api/projects/status/ya6xt30mxfnvplna?svg=true)](https://ci.appveyor.com/project/wtsnz/obs-ios-camera-source)
[![Build Status](https://travis-ci.org/wtsnz/obs-ios-camera-source.svg?branch=master)](https://travis-ci.org/wtsnz/obs-ios-camera-source)

To use this you use the [accompanying iOS app](https://will.townsend.io/products/obs-iphone/) to begin streaming in OBS.


## Downloads

Binaries for Windows and Mac are available in the [Releases](https://github.com/wtsnz/obs-ios-camera-source/releases) section.

## Building

You can run the CI scripts to build it. They will clone and build OBS Studio prior to building this plugin.

    ./CI/install-dependencies-macos.sh
    ./CI/install-build-obs-macos.sh
    ./CI/build-macos.sh
    ./CI/package-macos.sh


## Special thanks
- The entire [obs-websockets](https://github.com/Palakis/obs-websocket) project for providing a stella example of an obs plugin build pipeline!