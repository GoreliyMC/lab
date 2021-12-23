cmake_minimum_required(VERSION 3.5)

project(lab LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(SOURCES
    Window.cpp
    DemoWindow.cpp
    Coords.cpp
    Map.cpp
    Player.cpp
    )
set(HEADERS
    Window.h
    DemoWindow.h
    Coords.h
    Map.h
    Player.h
    )
find_package(SDL2 REQUIRED)
find_package(OpenGL REQUIRED)

include_directories(lab${SDL2_INCLUDE_DIRS})
include_directories(${OPENGL_INCLUDE_DIRS})

add_executable(lab main.cpp ${SOURCES} ${HEADERS})
target_link_libraries(lab ${SDL2_LIBRARIES} ${OPENGL_LIBRARIES})
