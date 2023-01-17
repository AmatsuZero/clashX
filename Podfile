source 'https://cdn.cocoapods.org/'
inhibit_all_warnings!

def common_pods
  pod 'Alamofire', '~> 5.0'
  pod 'SwiftyJSON'
  pod 'RxSwift'
  pod 'RxCocoa'
  pod 'CocoaLumberjack/Swift'
  pod 'Starscream','3.1.1'
end

target 'ClashX' do
  platform :osx, '10.13'
  use_modular_headers!

  common_pods
  pod 'WebViewJavascriptBridge'
  pod 'LetsMove'
  pod 'AppCenter/Analytics'
  pod 'Sparkle','~>1.0'
  pod "FlexibleDiff"
  pod 'GzipSwift'
end

target 'ClashiOS' do
  platform :ios, '11.0'
  common_pods
  pod 'WebViewJavascriptBridge', :modular_headers => true
  pod 'SnapKit', '~> 5.6.0'
end

target 'ClashiOSTests' do 

end

target 'ClashiOSTests' do

end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      if ['FlexibleDiff'].include? target.name
        target.build_configurations.each do |config|
          config.build_settings['SWIFT_VERSION'] = '5'
        end
      end
      if config.build_settings['MACOSX_DEPLOYMENT_TARGET'] == ''
        config.build_settings['MACOSX_DEPLOYMENT_TARGET'] = '10.13'
      end
    end
  end
end