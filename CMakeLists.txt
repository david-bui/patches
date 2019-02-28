# Anchor target : necessary to have the location of the private patches
# and ordering patches.
# this target should be built as soon as possible
# add_custom_target( dummy_webrtc_pvtpatches_target ALL
#   DEPENDS dummy_pvtpatches
#   )

# add_custom_command( OUTPUT dummy_pvtpatches 
#   COMMAND ${CMAKE_COMMAND} -E touch dummy_pvtpatches 
#   COMMENT "Fake target for Private Patches"
#   )

add_custom_target( dummy_webrtc_pvtpatches_target 
  )

add_custom_command( TARGET dummy_webrtc_pvtpatches_target PRE_BUILD 
  COMMAND ${CMAKE_COMMAND} -E touch dummy_pvtpatches
  COMMENT "Fake target for Private Patches"
  )