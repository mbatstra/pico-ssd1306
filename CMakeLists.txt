cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(pico_ssd1306_project C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
pico_sdk_init()

add_library(pico_ssd1306 src/ssd1306.c)

target_include_directories(pico_ssd1306 PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)
target_include_directories(pico_ssd1306 PRIVATE ${CMAKE_CURRENT_LIST_DIR}/src)

target_link_libraries(pico_ssd1306
  pico_stdlib
  hardware_i2c
)
