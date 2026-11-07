# Keep this aligned with IPHONEOS_DEPLOYMENT_TARGET in the Xcode project.
platform :ios, '15.4'

target 'iLiDAR' do
  pod 'CocoaAsyncSocket'
  source 'https://github.com/CocoaPods/Specs.git'
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '15.4'
    end
  end
end
