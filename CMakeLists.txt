cmake_minimum_required(VERSION 3.21)

# Define the AES Crypt GUI project for Unix-Like Systems
project(aescrypt_gui
        VERSION 4.3.1.1
        DESCRIPTION "AES Crypt Graphical User Interface (GUI) for Unix-Like Systems"
        HOMEPAGE_URL "https://www.aescrypt.com")

# Tests are built by default when this is a top-level project
if(PROJECT_IS_TOP_LEVEL)
    option(aescrypt_gui_BUILD_TESTS "Build Tests for the AES Crypt GUI" ON)
else()
    option(aescrypt_gui_BUILD_TESTS "Build Tests for the AES Crypt GUI" OFF)
endif()

# Option to control ability to install the program
option(aescrypt_gui_INSTALL "Install the AES Crypt GUI Program" ON)

include(CTest)

add_subdirectory(dependencies)
add_subdirectory(src)

# Include packaging only if this is the top-level project
if(PROJECT_IS_TOP_LEVEL)
    add_subdirectory(packaging)
endif()
