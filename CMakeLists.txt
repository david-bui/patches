#[[ 
Author : David Bui <david.bui@cosmosoftware.io>
Usage : The folder Patches will be added by libwebrtc-cmake
You can use macros and function from libwebrtc-cmake project in Patches folder,
not in this current CMakeLists.txt

- Add your patches into the folder called Patches
- First patch must have a dependency on "webrtc_synchronization"
- "webrtc_patch_end" must have a dependency on the last patch

Anchor target "webrtc_pvtpatches": necessary to have the location of the private patches (target property)
and patches ordering. This file should be added to the build system to make the target available.
Then use include() to the main CMakeLists in the Patches folder.
]]

add_custom_target( webrtc_pvtpatches ALL )