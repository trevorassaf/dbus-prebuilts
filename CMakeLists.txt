cmake_minimum_required(VERSION 3.1)

include_directories(include/dbus-1.12.20)

file(GLOB DBUS_PREBUILT_LIBRARIES "lib/*.so*")
message("LIBRARIES = ${DBUS_PREBUILT_LIBRARIES}")
target_link_libraries(dbus_test ${DBUS_PREBUILT_LIBRARIES})

add_library(dbus SHARED IMPORTED)
set_property(TARGET dbus PROPERTY IMPORTED_LOCATION "lib/libdbus-1.so")
