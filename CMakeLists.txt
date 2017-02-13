cmake_minimum_required(VERSION 3.5)
project(ios-deploy VERSION 0.0.1 LANGUAGES C)

set(CMAKE_FIND_ROOT_PATH_MODE_PROGRAM NEVER)
set(CMAKE_FIND_ROOT_PATH_MODE_LIBRARY NEVER)
set(CMAKE_FIND_ROOT_PATH_MODE_INCLUDE NEVER)

find_library(FOUNDATION      Foundation)
find_library(CORE_FOUNDATION CoreFoundation)
find_library(MOBILE_DEVICE   MobileDevice PATHS /System/Library/PrivateFrameworks)

add_executable(ios-deploy ios-deploy.c)
target_compile_options(ios-deploy PUBLIC -ObjC)
target_link_libraries(ios-deploy PUBLIC ${FOUNDATION} ${CORE_FOUNDATION} ${MOBILE_DEVICE})

