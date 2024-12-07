cmake_minimum_required(VERSION 3.22)

#
# This file is generated only once,
# and is not re-generated if converter is called multiple times.
#
# User is free to modify the file as much as necessary
#

# Setup compiler settings
set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_C_EXTENSIONS ON)


# Define the build type
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Debug")
endif()

# Set the project name
set(CMAKE_PROJECT_NAME BLE_v1)

# Include toolchain file
include("cmake/gcc-arm-none-eabi.cmake")

# Enable compile command to ease indexing with e.g. clangd
set(CMAKE_EXPORT_COMPILE_COMMANDS TRUE)

# Enable CMake support for ASM and C languages
enable_language(C ASM)

# Core project settings
project(${CMAKE_PROJECT_NAME})
message("Build type: " ${CMAKE_BUILD_TYPE})

# Create an executable object type
add_executable(${CMAKE_PROJECT_NAME})

# Add STM32CubeMX generated sources
add_subdirectory(cmake/stm32cubemx)

# Link directories setup
target_link_directories(${CMAKE_PROJECT_NAME} PRIVATE
    # Add user defined library search paths
)

# Add sources to executable
target_sources(${CMAKE_PROJECT_NAME} PRIVATE
    # Add user sources here
        STM32_WPAN/App/dis.c
        STM32_WPAN/App/dis_app.c
        STM32_WPAN/App/hrs.c
        STM32_WPAN/App/hrs_app.c
        Drivers/u8g2/u8x8_d_ssd1306_128x64_noname.c
        Drivers/u8g2/u8x8_display.c
        Drivers/u8g2/u8g2_d_memory.c
        Drivers/u8g2/u8g2_d_setup.c
        Core/Src/stm32_u8g2.c
        Drivers/u8g2/u8x8_cad.c
        Drivers/u8g2/u8x8_gpio.c
        Drivers/u8g2/mui.c
        Drivers/u8g2/mui_u8g2.c
        Drivers/u8g2/u8g2_arc.c
        Drivers/u8g2/u8g2_bitmap.c
        Drivers/u8g2/u8g2_box.c
        Drivers/u8g2/u8g2_buffer.c
        Drivers/u8g2/u8g2_button.c
        Drivers/u8g2/u8g2_circle.c
        Drivers/u8g2/u8g2_cleardisplay.c
        Drivers/u8g2/u8g2_d_memory.c
        Drivers/u8g2/u8g2_d_setup.c
        Drivers/u8g2/u8g2_font.c
        Drivers/u8g2/u8g2_fonts.c
        Drivers/u8g2/u8g2_hvline.c
        Drivers/u8g2/u8g2_input_value.c
        Drivers/u8g2/u8g2_intersection.c
        Drivers/u8g2/u8g2_kerning.c
        Drivers/u8g2/u8g2_line.c
        Drivers/u8g2/u8g2_ll_hvline.c
        Drivers/u8g2/u8g2_message.c
        Drivers/u8g2/u8g2_polygon.c
        Drivers/u8g2/u8g2_selection_list.c
        Drivers/u8g2/u8g2_setup.c
        Drivers/u8g2/u8log.c
        Drivers/u8g2/u8log_u8g2.c
        Drivers/u8g2/u8log_u8x8.c
        Drivers/u8g2/u8x8_8x8.c
        Drivers/u8g2/u8x8_byte.c
        Drivers/u8g2/u8x8_cad.c
        Drivers/u8g2/u8x8_capture.c
        Drivers/u8g2/u8x8_debounce.c
        Drivers/u8g2/u8x8_display.c
        Drivers/u8g2/u8x8_d_ssd1306_128x64_noname.c
        Drivers/u8g2/u8x8_fonts.c
        Drivers/u8g2/u8x8_gpio.c
        Drivers/u8g2/u8x8_input_value.c
        Drivers/u8g2/u8x8_message.c
        Drivers/u8g2/u8x8_selection_list.c
        Drivers/u8g2/u8x8_setup.c
        Drivers/u8g2/u8x8_string.c
        Drivers/u8g2/u8x8_u16toa.c
        Drivers/u8g2/u8x8_u8toa.c
)

# Add include paths
target_include_directories(${CMAKE_PROJECT_NAME} PRIVATE
    # Add user defined include paths
        STM32_WPAN/App
        Drivers/u8g2
)

# Add project symbols (macros)
target_compile_definitions(${CMAKE_PROJECT_NAME} PRIVATE
    # Add user defined symbols
)

# Add linked libraries
target_link_libraries(${CMAKE_PROJECT_NAME}
    stm32cubemx

    # Add user defined libraries
)
