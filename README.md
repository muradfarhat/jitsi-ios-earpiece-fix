# Jitsi Meet iOS SDK – Earpiece Audio Fix (Custom Build)
Overview
This repository contains a custom-built version of the Jitsi Meet iOS SDK where the default
audio output has been modified to improve the call experience:
■ Audio Calls → Default output: Earpiece
■ Video Calls → Default output: Speaker
This behavior differs from the official SDK, which routes all audio (including voice-only calls)
through the speaker by default.
What Was Changed
The modification was made in the following file of the Jitsi Meet iOS SDK source:
JitsiMeetSDK/AudioMode.m
Changes made:
- Updated the audio session configuration to make the earpiece the default route for audio calls.
- Kept the speaker as the default route for video calls.
After editing, the SDK was rebuilt into an .xcframework following the official Jitsi build
instructions.
Building the Framework
The SDK was built using the official method described in the Jitsi documentation:
Building the Jitsi Meet iOS SDK
Steps followed:
1. Cloned the official Jitsi Meet repository.
2. Edited AudioMode.m to modify the default audio routing behavior.
3. Built the .xcframework using the provided Gradle and Xcode scripts.
4. Integrated the resulting JitsiMeetSDK.xcframework manually into the iOS project.
Dependencies
To use this custom SDK locally, you need to add:
- JitsiMeetSDK.xcframework
- Hermes.xcframework
Both should be added locally to your iOS project (not through CocoaPods or SPM).
Integration (Manual)
1. Clone or download this repository.
2. Drag and drop the following frameworks into your Xcode project:
- JitsiMeetSDK.xcframework
- Hermes.xcframework
3. Ensure “Embed & Sign” is selected in your target’s “Frameworks, Libraries, and Embedded
Content” section.
4. Clean and rebuild your project.
Notes
- This build is based on the official Jitsi Meet iOS SDK with minor audio configuration changes.
- All copyrights and trademarks belong to Jitsi / 8x8, Inc.
- This repository is provided for educational and development purposes only.
Author
Murad Farhat
Software Engineer – iOS | Android | Flutter
■ Dubai, UAE
