cmake_minimum_required(VERSION 3.20)
project(soil C)

find_package(OpenGL REQUIRED)

add_subdirectory(cmake/stb)

file(GLOB SOURCES src/*.c)
file(GLOB HEADERS include/SOIL/*.h)

add_library(soil SHARED ${SOURCES} ${HEADERS})
target_link_libraries(soil PRIVATE stb OpenGL::GL)
target_include_directories(soil PUBLIC include)

if (WIN32)
    target_compile_definitions(soil PRIVATE _CRT_SECURE_NO_WARNINGS)
endif ()
