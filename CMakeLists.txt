cmake_minimum_required(VERSION 3.20)
project(soil C)

add_subdirectory(cmake/stb)

file(GLOB SOURCES src/*.c)
file(GLOB HEADERS include/SOIL/*.h)

add_library(soil SHARED ${SOURCES} ${HEADERS})
target_link_libraries(soil PRIVATE stb)
target_include_directories(soil PUBLIC include)
