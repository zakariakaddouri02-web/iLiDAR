## Full Tutorial

If you want to build this project from scratch or make significant modifications, follow this tutorial:

### Run Official Example

First, download the official example from:

```
https://developer.apple.com/documentation/avfoundation/additional_data_capture/capturing_depth_using_the_lidar_camera
```

This is a Swift project, but you can proceed even if you're not familiar with Swift. Extract the project and move it into your project folder. Then, try to compile and run it on your iPhone. You may need to handle connection issues (set your device as the build target, trust your macOS on the iPhone) or development permissions (register a development team and log in). Once the build succeeds, you will see your iPhone capturing depth data and RGB images, which will be visualized on the screen.

### Set the Third-party Extension

To manage third-party extensions, you need to install [cocoapods](https://cocoapods.org/) via `gem`:

```bash
# one possible download method
brew gem install cocoapods
cd LiDARDepth
pod init
```

Modify the generated `Podfile` to:

```ini
# Uncomment the next line to define a global platform for your project
# platform :ios, '15.6'

target 'LiDARDepth' do
  pod 'CocoaAsyncSocket'
  pod 'ReactiveCocoa', '~> 11.0'
  source 'https://github.com/CocoaPods/Specs.git'
  
end
```
Then, run

```bash
pod install
```

After installation, open `iLiDAR.xcworkspace`. The app target is `iLiDAR`; CocoaPods adds its `Pods-iLiDAR` support target.

### (Optional) Possible Troubleshooting

By default, the configuration files might be incorrect. You may encounter the following error:

```bash
[Error] The sandbox is not in sync with the Podfile.lock. Run 'pod install' or update your CocoaPods installation.
```

Run `pod install` from the repository root and open `iLiDAR.xcworkspace`. The app target's Debug and Release base configurations must resolve to `Pods/Target Support Files/Pods-iLiDAR/Pods-iLiDAR.debug.xcconfig` and `Pods/Target Support Files/Pods-iLiDAR/Pods-iLiDAR.release.xcconfig`. Do not select or archive the CocoaPods target as the application.

### Replace Code

Once the project builds without errors, you can start writing your own depth camera app with network support.
