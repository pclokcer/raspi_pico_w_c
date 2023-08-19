set(PROJECT tcp-client)

cmake_minimum_required(VERSION 3.10)

# defined pico W
set(PICO_BOARD pico_w)

include($ENV{PICO_SDK_PATH}\\pico_sdk_init.cmake)

project(${PROJECT} C CXX ASM)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

pico_sdk_init()

add_executable(${PROJECT}
  client.c
)

target_include_directories(${PROJECT} PRIVATE
        ${CMAKE_CURRENT_LIST_DIR}
        ${CMAKE_CURRENT_LIST_DIR}/.. # for our common lwipopts
        )
target_link_libraries(${PROJECT}
        pico_cyw43_arch_lwip_threadsafe_background
        pico_stdlib
        )
pico_add_extra_outputs(${PROJECT})