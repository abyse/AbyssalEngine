cmake_minimum_required(VERSION 3.7)
project(Glad)

add_library(glad STATIC include/glad/gl.h src/gl.c)
target_include_directories(glad PUBLIC include/)