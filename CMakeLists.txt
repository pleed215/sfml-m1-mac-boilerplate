cmake_minimum_required(VERSION 3.22)
project(boilerplate)

set(CMAKE_CXX_STANDARD 14)
set(SFML_INCLUDE_DIR "/opt/homebrew/Cellar/sfml/2.5.1_1/include")
set(SFML_LIBRARY_DIR "/opt/homebrew/Cellar/sfml/2.5.1_1/lib")
set(SFML_DIR "/opt/homebrew/Cellar/sfml/2.5.1_1/lib/cmake/SFML")

link_directories(/opt/homebrew/Cellar/sfml/2.5.5.1_1/lib)
include_directories(/opt/homebrew/Cellar/sfml/2.5.5.1_1/include)

find_package(SFML 2.5.1 COMPONENTS system window graphics network audio)
if(SFML_FOUND)
    message(STATUS "SFML_INCLUDE_DIR: ${SFML_INCLUDE_DIR}")
    message(STATUS "SFML_LIBRARIES: ${SFML_LIBRARIES}")
    message(STATUS "SFML_VERSION: ${SFML_VERSION}")
endif()

add_executable(boilerplate main.cpp)
target_link_libraries(boilerplate sfml-graphics sfml-window sfml-system)