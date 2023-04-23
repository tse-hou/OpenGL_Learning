cmake_minimum_required(VERSION 3.0.0)
project(HelloWorld VERSION 0.1.0)

include(CTest)
enable_testing()
include_directories(../include)
link_directories(../lib)
find_library(COCOA_LIBRARY Cocoa REQUIRED)
find_library(IOKIT_LIBRARY IOKit REQUIRED)
find_library(COREVID_LIBRARY CoreVideo REQUIRED)

add_executable(HelloWorld main.cpp glad.c)
target_link_libraries(HelloWorld libglfw3.a)
target_link_libraries(HelloWorld ${COCOA_LIBRARY} ${COREVID_LIBRARY} ${IOKIT_LIBRARY})

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
