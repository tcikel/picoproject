cmake_minimum_required(VERSION 3.12)
set(PICO_BOARD pico_w)
include(pico_sdk_import.cmake)
project(picow_blink C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(PICO_EXAMPLES_PATH ${PROJECT_SOURCE_DIR})

pico_sdk_init()
add_executable(picow_blink
        picow_blink.c
        )

target_link_libraries(picow_blink
        pico_stdlib              # for core functionality
        pico_cyw43_arch_none     # we need Wifi to access the GPIO, but we don't need anything else
        )

# create map/bin/hex file etc.
pico_add_extra_outputs(picow_blink)

# add url via pico_set_program_url
#example_auto_set_url(picow_blink)
