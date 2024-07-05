cmake_minimum_required(VERSION 3.25)

message("Building...")

set(OUTPUT_NAME gfx_pack_demo)
set(SDK_PATH $ENV{PICO_SDK_PATH})

message("Path: ${SDK_PATH}.")

include(${SDK_PATH}/external/pico_sdk_import.cmake)
pico_sdk_init()

add_executable(${OUTPUT_NAME} gfx_demo.cpp)

project(lcd_test C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Pull in pico libraries that we need
target_link_libraries(${OUTPUT_NAME} pico_stdlib)

# create map/bin/hex file etc.
pico_add_extra_outputs(${OUTPUT_NAME})

add_subdirectory(common)
add_subdirectory(libraries)
