cmake_minimum_required(VERSION 2.8.4)
set(CMAKE_TOOLCHAIN_FILE ${CMAKE_SOURCE_DIR}/cmake/ArduinoToolchain.cmake)
set(CMAKE_CXX_STANDARD 98)
set(PROJECT_NAME ugclibexample)

set(${PROJECT_NAME}_BOARD uno)
project(${PROJECT_NAME})

# Define additional source and header files or default arduino sketch files

### Additional static libraries to include in the target.

### Main sketch file
set(${PROJECT_NAME}_SKETCH ugclibexample.ino)

### Add project directories into the build

### Additional settings to add non-standard or your own Arduino libraries.
# For this example (libs will contain additional arduino libraries)
# An Arduino library my_lib will contain files in libs/my_lib/: my_lib.h, my_lib.cpp + any other cpp files

# For nested library sources replace ${LIB_NAME} with library name for each library
# set(_RECURSE true)

#### Additional settings for programmer. From programmers.txt
set(${PROJECT_NAME}_PROGRAMMER arduinoasisp)
set(${PROJECT_NAME}_PORT /dev/ttyACM0)
set(uno.upload.speed 9600)

## Verbose build process

generate_arduino_firmware(${PROJECT_NAME})


print_board_list()
print_programmer_list()
