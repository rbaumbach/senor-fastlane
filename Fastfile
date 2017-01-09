# This is the minimum version number required.
# Update this, if you use features of a newer version
fastlane_version "2.3.0"

default_platform :ios

platform :ios do
  before_all do
    puts "🌯 🌯 🌯 Doin' some fastlane 🌯 🌯 🌯"
  end

  desc "Submit TestFlight build to internal testers"
  lane :testflight_internal do
    increment_build_number
    commit_version_bump

    gym(scheme: "StickerPackExtension",
        silent: true,
        clean: true,
        include_symbols: true,
        include_bitcode: true)

    xcarchive(scheme: "StickerPackExtension")

    pilot
  end

  after_all do |lane|
    puts "🌮 🌮 🌮  Taco Time! 🌮 🌮 🌮"
  end

  error do |lane, exception|
    puts "Uh oh..."
  end
end

# Things to investigate
# 1. Using match to handle the certs and provisioning profiles


# More information about multiple platforms in fastlane: https://github.com/fastlane/fastlane/blob/master/fastlane/docs/Platforms.md
# All available actions: https://docs.fastlane.tools/actions

# fastlane reports which actions are used
# No personal data is recorded. Learn more at https://github.com/fastlane/enhancer