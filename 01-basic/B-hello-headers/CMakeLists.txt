# Set the minimum version of CMake that can be used
# To find the cmake version run
# $ cmake --version
cmake_minimum_required(VERSION 3.16)

# Set the project name
project (hello_headers)

# Create a sources variable with a link to all cpp files to compile
set(SOURCES
    src/Hello.cpp
    src/main.cpp
)

set(HEADERS include/Hello.h)

INCLUDE_DIRECTORIES(SYSTEM ${CMAKE_CURRENT_SOURCE_DIR}/include)


source_group(TREE ${CMAKE_SOURCE_DIR} FILES ${HEADERS})
source_group(TREE ${CMAKE_SOURCE_DIR} FILES ${SOURCES})


# Add an executable with the above sources
add_executable(hello_headers ${SOURCES} ${HEADERS})

# Set the directories that should be included in the build command for this target
# when running g++ these will be included as -I/directory/path/

#target_include_directories(hello_headers
#    PUBLIC
#        ${PROJECT_SOURCE_DIR}/include
#		${PROJECT_SOURCE_DIR}/src
#)

