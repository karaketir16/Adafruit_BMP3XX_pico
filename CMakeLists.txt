cmake_minimum_required(VERSION 3.13)

# initialize the SDK based on PICO_SDK_PATH
# note: this must happen before project()
include(pico_sdk_import.cmake)

project(bmp3xx_lib_project)


# initialize the Raspberry Pi Pico SDK
pico_sdk_init()

add_library(bmp3xx STATIC 
    bmp3.c
    Adafruit_BMP3XX.cpp
)

target_link_libraries(bmp3xx pico_stdlib hardware_i2c)

target_include_directories(bmp3xx INTERFACE .)

