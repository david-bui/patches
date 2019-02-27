add_custom_target( PvtPatches ALL )

get_property(fancy_lib_location TARGET PvtPatches PROPERTY LOCATION)
message (STATUS "fancy_lib_location == ${fancy_lib_location}")