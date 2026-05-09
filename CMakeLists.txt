cmake_minimum_required(VERSION 3.10)
project(ChaPar LANGUAGES CXX)

#TODO: Encapsulate this
# --------------------------------------------------
if(CMAKE_SOURCE_DIR STREQUAL PROJECT_SOURCE_DIR)
    set(ChaPar_Is_Top_Level_Project ON)
else()
    set(ChaPar_Is_Top_Level_Project OFF)
endif()

if (ChaPar_Is_Top_Level_Project)
    set(CMAKE_CXX_STANDARD 11)
endif ()
# --------------------------------------------------

add_subdirectory(Vendor)

# TODO: move this to its own lib after first implementation
add_executable(ChaPar main.cpp)
target_link_libraries(ChaPar PUBLIC CommonCPP)
