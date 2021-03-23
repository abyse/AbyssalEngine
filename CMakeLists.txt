cmake_minimum_required(VERSION 3.7 FATAL_ERROR)

project(AbyssalEngine)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/glad/include)

file(GLOB source_files "*.h" "*.cpp" "main/*.cpp" "src/*.cpp" "include/*.h" "include/*.hpp" ${CMAKE_CURRENT_SOURCE_DIR} *.c glad/src/gl.c)

add_executable(AbyssalEngine ${source_files})

include(FindPkgConfig)
pkg_search_module(SDL2 REQUIRED sdl2)
target_include_directories(${PROJECT_NAME} PRIVATE ${SDL2_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} PRIVATE ${SDL2_LIBRARIES})

