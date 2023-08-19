set(PROJECT blink)

cmake_minimum_required(VERSION 3.10)

# defined pico W
set(PICO_BOARD pico_w)

include($ENV{PICO_SDK_PATH}\\pico_sdk_init.cmake)

project(${PROJECT} C CXX ASM)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

pico_sdk_init()

add_executable(${PROJECT}
  blink.c
)

pico_enable_stdio_usb(${PROJECT} 1)
pico_enable_stdio_uart(${PROJECT} 1)

pico_add_extra_outputs(${PROJECT})

target_link_libraries(${PROJECT} 
    pico_stdlib
    pico_cyw43_arch_none
    )