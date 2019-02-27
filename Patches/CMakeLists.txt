# Copyright 2015, 2016, 2017, 2018 Dr Alex Gouaillard <agouaillard@gmail.com>

# Needed to disable building llvm thin libs, that MSVC linker doesn't understand
set_webrtc_patch_target(
  "${GIT_APPLY_CMD}"
  src
  no_llvm_thin_lib.patch
  no_llvm_thin_lib
  webrtc_synchronization
  )
list(APPEND PATCHED_DIRS src )

# always close the dependency chain to make sure that all patches
# have been applied before you generate the ninja files and build
add_dependencies( webrtc_patch_end 
  Apply_no_llvm_thin_lib
  )