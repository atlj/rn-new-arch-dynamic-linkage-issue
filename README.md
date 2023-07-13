# Issue with building new architecture app on iOS when `use_frameworks` is set to `dynamic` linkage

This is a repository to reproduce an error caused by calling `use_frameworks` with `dynamic` linkage on the new React Native architecture.

The build fails due to:
```
Undefined symbol: facebook::react::ImageManager::requestImage(facebook::react::ImageSource const&, int) const
```
<details>
  <summary>You can see the whole issue here</summary>

```
Showing All Errors Only

Build target React-Fabric of project Pods with configuration Debug
warning: Run script build phase 'Create Symlinks to Header Folders' will be run during every build because it does not specify any outputs. To address this warning, either add output dependencies to the script phase, or configure it to run in every build by unchecking "Based on dependency analysis" in the script phase. (in target 'React-Fabric' from project 'Pods')


Ld /Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-Fabric/React_Fabric.framework/React_Fabric normal (in target 'React-Fabric' from project 'Pods')
    cd /Users/burakguner/kod/testDynamicLatest/ios/Pods
    /Applications/Xcode-14.2.0.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/clang++ -target arm64-apple-ios12.4-simulator -dynamiclib -isysroot /Applications/Xcode-14.2.0.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator16.2.sdk -L/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Intermediates.noindex/EagerLinkingTBDs -L/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-Fabric -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Intermediates.noindex/EagerLinkingTBDs -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-Fabric -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/DoubleConversion -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/RCT-Folly -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/RCTTypeSafety -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-Core -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-cxxreact -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-debug -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-graphics -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-hermes -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-jsi -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-jsiexecutor -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-jsinspector -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-logger -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-perflogger -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-runtimescheduler -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-utils -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/ReactCommon -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/SocketRocket -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/Yoga -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/fmt -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/glog -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/libevent -F/Users/burakguner/kod/testDynamicLatest/ios/Pods/hermes-engine/destroot/Library/Frameworks/universal -F/Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/XCFrameworkIntermediates/hermes-engine/Pre-built -filelist /Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Intermediates.noindex/Pods.build/Debug-iphonesimulator/React-Fabric.build/Objects-normal/arm64/React_Fabric.LinkFileList -install_name @rpath/React_Fabric.framework/React_Fabric -Xlinker -rpath -Xlinker @executable_path/Frameworks -Xlinker -rpath -Xlinker @loader_path/Frameworks -dead_strip -Xlinker -object_path_lto -Xlinker /Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Intermediates.noindex/Pods.build/Debug-iphonesimulator/React-Fabric.build/Objects-normal/arm64/React_Fabric_lto.o -Xlinker -export_dynamic -Xlinker -no_deduplicate -Xlinker -objc_abi_version -Xlinker 2 -stdlib\=libc++ -fobjc-arc -fobjc-link-runtime -framework DoubleConversion -framework JavaScriptCore -framework RCTTypeSafety -framework React -framework ReactCommon -framework React_debug -framework React_graphics -framework React_runtimescheduler -framework React_utils -framework folly -framework glog -framework hermes -framework jsi -framework jsireact -framework logger -framework yoga -framework Foundation -Xlinker -no_adhoc_codesign -compatibility_version 1 -current_version 1 -Xlinker -dependency_info -Xlinker /Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Intermediates.noindex/Pods.build/Debug-iphonesimulator/React-Fabric.build/Objects-normal/arm64/React_Fabric_dependency_info.dat -o /Users/burakguner/Library/Developer/Xcode/DerivedData/testDynamicLatest-ccdudyxjtfwmbvgujomkmpjyasud/Build/Products/Debug-iphonesimulator/React-Fabric/React_Fabric.framework/React_Fabric

Undefined symbols for architecture arm64:
  "facebook::react::ImageManager::requestImage(facebook::react::ImageSource const&, int) const", referenced from:
      facebook::react::ImageShadowNode::updateStateIfNeeded() in ImageShadowNode.o
ld: symbol(s) not found for architecture arm64
clang: error: linker command failed with exit code 1 (use -v to see invocation)

Undefined symbol: facebook::react::ImageManager::requestImage(facebook::react::ImageSource const&, int) const



Build failed    13.07.2023 12:40    45.1 seconds
```
</details>

## What is changed?

I've added these lines to the [Podfile](./ios/Podfile):
``` ruby
ENV["RCT_NEW_ARCH_ENABLED"]="1"
ENV['NO_FLIPPER'] = '1'
ENV['USE_FRAMEWORKS'] = 'dynamic'
```

## How to reproduce

1. Install the npm dependencies.
2. Install the pods.
3. Build the app either via `XCode` or using `react-native run-ios`
