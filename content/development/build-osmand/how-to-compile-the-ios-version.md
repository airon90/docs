---
title: How to Compile the iOS Version
versions: '*'
---

#### **1. Install XCode from AppStore (not BETA!)**
#### **2. Install XCode command-line tools:** 
```
$ xcode-select --install
```
Or in case of errors try to dowlnload and install it from Apple site:
```
https://developer.apple.com/download/more/?name=for%20Xcode
```
#### **3. Install CMake (exactly this version!):**
```
https://github.com/Kitware/CMake/releases/download/v3.11.2/cmake-3.11.2-Darwin-x86_64.dmg
```
Open your .zshrc file: 
```
$ sudo nano .zshrc
```
Add this line and save file: 
```
PATH="/Applications/CMake.app/Contents/bin":"$PATH"
```
Reload your .zshrc file: 
```
$ source ~/.zshrc
```
Verify everything works: 
```
$ cmake --version
```
#### **4. Create folder for OsmAnd repositories**
```
$ mkdir OsmAnd && cd OsmAnd
```
#### **5. Clone all OsmAnd repositories:**
```
$ git clone https://github.com/osmandapp/OsmAnd-build.git build
$ git clone https://github.com/osmandapp/OsmAnd-core.git core
$ git clone https://github.com/osmandapp/OsmAnd-core-legacy.git core-legacy
$ git clone https://github.com/osmandapp/OsmAnd-ios.git ios
$ git clone https://github.com/osmandapp/Osmand.git -b master android
$ git clone https://github.com/osmandapp/OsmAnd-resources.git resources
$ git clone https://github.com/osmandapp/osmandapp.github.io.git help
```
#### **6. Run prepare.sh**
```
$ cd ios
$ ./prepare.sh
```
In case of error `Xcode not set up properly. You may need to confirm the license...`:

switch XCodeCommandLineTools to XCode app, confirm the license and swith it back.

```
$ sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
$ sudo xcodebuild -license accept
$ sudo xcode-select --switch /Library/Developer/CommandLineTools
```
If you still have an error `Xcode not set up properly. You may need to confirm the license...` then need check if xcrun is available:
```
/usr/bin/xcrun -find xcrun
```
If you got:
```
xcrun: error: unable to find utility "xcrun", not a developer tool or in PATH
```
Then open Xcode > Preferences > Locations and in field "Command Line Tools" select your command line tools "Xcode 12.4"

Or in case of another errors:
Get your XCode CLang version number.
```
$ ls /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/lib/clang/
12.0.0
```
Replace `{CLANG_VERSION}` in this command with your version and open file:
```
$ sudo nano /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/lib/clang/{CLANG_VERSION}/include/ia32intrin.h
example:
$ sudo nano /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/lib/clang/12.0.0/include/ia32intrin.h
```
Comment this lines and save file.
```
#define _bit_scan_forward(A) __bsfd((A))
#define _bit_scan_reverse(A) __bsrd((A))
```
And run `$ ./prepare.sh` again.
#### **7. Open osmand.xcworkspace in XCode.**
#### **8. First build.**
Set the build target to `OsmAnd Maps`. 
Selet as target your device or as one of IOS simulators. But don't use default 'Any IOS Device (arm64)'. 
Build the project.

In case of build erros you can press in XCode: 
```
Product -> Clean build folder
```
Then close XCode. 
Delete `baked` and `binaries` folders in `OsmAnd` directory (if it already exists). 
Delete XCode DerivedData folder:
```
sudo rm -R ~/Library/Developer/Xcode/DerivedData/*
```
Check that all repositories are up to date.
Then run `$ ./prepare.sh` and try to build the project again.
