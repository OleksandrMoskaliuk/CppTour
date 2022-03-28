CMAKE_MINIMUM_REQUIRED(VERSION 3.2)
project(MyApp VERSION 1.0
        LANGUAGES CXX
        )

set(CMAKE_CXX_STANDARD 17) # add flag c++17
#set(CMAKE_EXPORT_COMPILE_COMMANDS ON)   #important
set(CMAKE_CXX_COMPILE_FEATURES "-Wall -Wextra") #All warnings while compiling
set(CMAKE_EN_FLAGS_DEBUGBUG "-g -0o")
set(SFML_STATIC_LIBRARIES FALSE) # Use sfml with dynamic libraries
set(SFML_DIR c:/SFML/lib/cmake/SFML)

include_directories(C:/SFML/include)
include_directories(${PROJECT_SOURCE_DIR}/app/include)
include_directories(${PROJECT_SOURCE_DIR}/include)

find_package(SFML COMPONENTS system window graphics audio network REQUIRED) #looking for SFML

add_executable(${PROJECT_NAME}
        ${PROJECT_SOURCE_DIR}/TestSFML/main.cpp)

# Linking SFML libraries to executable target
target_link_libraries(${PROJECT_NAME}
        sfml-graphics
        sfml-system
        sfml-window
        sfml-audio
        )
