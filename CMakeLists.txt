# Copyright 2015, 2016, 2017, 2018 Dr Alex Gouaillard <agouaillard@gmail.com>

set_webrtc_patch_target(
  "${GIT_APPLY_CMD} --check"
  src
  customer1.patch
  customer1
  webrtc_synchronization
  )
list(APPEND PATCHED_DIRS src )

# always close the dependency chain to make sure that all patches
# have been applied before you generate the ninja files and build
add_dependencies( webrtc_patch_end 
  Apply_customer1
  )