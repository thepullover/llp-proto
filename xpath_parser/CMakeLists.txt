cmake_minimum_required(VERSION 3.21)
project(LLP2 C)

set(CMAKE_C_STANDARD 11)

include_directories(include/structure)
include_directories(include/parser)
include_directories(include/io)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CURRENT_SOURCE_DIR .)
set(SOURCES src/structure/view.c src/parser/parser.c src/io/printer.c src/XPParser.c)
set(HEADERS include/structure/state.h include/structure/view.h include/XPParser.h)

add_library(Xpath_lib SHARED ${SOURCES} ${HEADERS})
target_include_directories(Xpath_lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
