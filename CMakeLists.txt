# This file by
# Jorge Alberto Cervantes Montiel
# 08Jan2019
# 
# KeyCastOW
#
# Project git forked from https://github.com/brookhong/KeyCastOW 
#
# Main objective of this fork is compile under vs2017 with x64 support 
# with CMake generated project files. CMake is used to allow fast 
# compile under future visual studio versions.
#
cmake_minimum_required (VERSION 3.12)

project(KeyCastOW)

include_directories(src)
ADD_DEFINITIONS(-DUNICODE -D_UNICODE)
add_executable(keycastow 
	WIN32
	src/keycast.cpp 
	src/keylog.cpp 
	src/keycast.h 
	src/keylog.h 
	src/resource.h 
	src/timer.h 
	src/keycastow.rc
	src/keycastow.ico)
target_link_libraries(keycastow gdiplus.lib ComCtl32.Lib)
source_group("Resource Files" FILES src/keycastow.ico src/keycastow.rc)
install(TARGETS keycastow RUNTIME DESTINATION bin)