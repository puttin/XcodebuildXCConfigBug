## Acknowledge & Steps
0. Xcode 7.3 (7D175), OS X 10.11.4 (15E65)
1. Project has a variable called "MY_CONFIGS" set to "QWER"
2. Target use a xcconfig named "1.xcconfig"
3. "1.xcconfig" include "base.xcconfig"
4. "base.xcconfig"'s "MY_CONFIGS" is `$(inherited) "ASDF" "ZXCV"`
5. `$ xcodebuild -showBuildSettings > withoutXCConfigArgumentResult.xcconfig`
6. `$ xcodebuild -showBuildSettings -xcconfig ./TestXcodebuildXCConfig/1.xcconfig > withXCConfigArgumentResult.xcconfig`
7. diff
8. "MY_CONFIGS" value is wrong

## man xcodebuild
> -xcconfig filename
> 
> Load the build settings defined in filename when building all targets.  These settings will override all other settings, including settings
           passed individually on the command line.
           
## Make sure you checkout diff & project file
fire issue if you confuse
