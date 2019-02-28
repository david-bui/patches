#[[ 
Author : David Bui <david.bui@cosmosoftware.io>
Usage : The folder Patches will be called by libwebrtc-cmake
You can use macros and function from libwebrtc-cmake project in Patches folder,
not in this current CMakeLists.txt

- Add your patches into the folder called Patches
- First patch must have a dependency on "webrtc_synchronization"
- "webrtc_patch_end" must have a dependency on the last patch

Anchor target "dummy_webrtc_pvtpatches_target": necessary to have the location of the private patches (target property)
and patches ordering
this target should be built as soon as possible to have access to needed information 
]]

# dummy_webrtc_pvtpatches_target will be always built
add_custom_target( dummy_webrtc_pvtpatches_target ALL
  )

# Build before compiling sources
add_custom_command( TARGET dummy_webrtc_pvtpatches_target PRE_BUILD 
  COMMENT "Fake target for Private Patches"
  )