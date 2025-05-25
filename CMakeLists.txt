cmake_minimum_required(VERSION 4.0)

#-Change to C for C ,CXX for Cpp-#
project(pong_game CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

#-Change it to your lib location-#
include_directories(C:/DevLib/raylib-mingw64/include) 
link_directories(C:/DevLib/raylib-mingw64/lib)

#-Check cpp file in root folder-#
#file(GLOB SOURCES "*.cpp")

#-Scan root and subfolder for cpp file-#
file(GLOB_RECURSE SOURCES "src/*.cpp")

add_executable(main ${SOURCES})
target_link_libraries(main raylib opengl32 gdi32 winmm user32 shell32)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
add_compile_options(-Wall -Wextra -pedantic -Werror)