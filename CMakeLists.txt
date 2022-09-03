cmake_minimum_required(VERSION 3.7 FATAL_ERROR)

project(AbyssalEngine)

set(CMAKE_CXX_FLAGS -Wall)
set(CMAKE_CXX_FLAGS -static-libgcc)
set(CMAKE_CXX_FLAGS -static-libstdc++)

set(BUILD_SHARED_LIBS  OFF)

add_compile_definitions(SDL_MAIN_HANDLED)

add_subdirectory(vendor)

add_executable(Engine ./main/main.cpp)

target_link_libraries(Engine
        PUBLIC
        glad
        PRIVATE
        ${CMAKE_DL_LIBS})

target_link_libraries(Engine
        PUBLIC
        SDL2)

target_link_libraries(Engine
        PUBLIC
        imgui)