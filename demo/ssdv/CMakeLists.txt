# -*- CMakeLists.txt generated by CodeLite IDE. Do not edit by hand -*-

cmake_minimum_required(VERSION 2.8.11)

# Project name
project(ssdv_demo)

# This setting is useful for providing JSON file used by CodeLite for code completion
set(CMAKE_EXPORT_COMPILE_COMMANDS 1)

# Set default locations
set(CL_OUTPUT_DIRECTORY ${CMAKE_CURRENT_LIST_DIR}/../cmake-build-Debug/output)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CL_OUTPUT_DIRECTORY})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CL_OUTPUT_DIRECTORY})
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CL_OUTPUT_DIRECTORY})

set(CONFIGURATION_NAME "Debug")

# Projects


# Top project
# Define some variables
set(PROJECT_ssdv_demo_PATH "${CMAKE_CURRENT_LIST_DIR}")
set(WORKSPACE_PATH "${CMAKE_CURRENT_LIST_DIR}/..")



#{{{{ User Code 1
# Place your code here

# --- Ssdv Begin. Do not edit by hand -----------------------------------------
# Modifies binary file paths if codelite is not used.
if (NOT CL_USED)
  set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
  set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
  set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
endif (NOT CL_USED)

find_package(ssdv REQUIRED)
find_package(radio REQUIRED)
find_package(SDL REQUIRED)
find_package(SDL_image REQUIRED)

link_directories(${SSDV_LIBRARY_DIRS} ${RADIO_LIBRARY_DIRS})
add_definitions(${SSDV_CFLAGS} ${RADIO_CFLAGS})
include_directories(BEFORE ${SSDV_INCLUDE_DIRS} ${RADIO_INCLUDE_DIRS} 
    ${SDL_INCLUDE_DIR} ${SDL_IMAGE_INCLUDE_DIRS})
list(APPEND LINK_OPTIONS ${SSDV_LIBRARIES} ${RADIO_LIBRARIES} 
    ${SDL_LIBRARY} ${SDL_IMAGE_LIBRARIES})
# --- Ssdv End. Do not edit by hand -------------------------------------------
#}}}}

include_directories(
    .
    .

)


# Compiler options
add_definitions(-g)
add_definitions(-O0)
add_definitions(-Wall)

# Linker options


if(WIN32)
    # Resource options
endif(WIN32)

# Library path
set(CMAKE_LDFLAGS "${CMAKE_LDFLAGS} -L. ")

# Define the C sources
set ( C_SRCS
    ${CMAKE_CURRENT_LIST_DIR}/ssdv_demo.c
)

set_source_files_properties(
    ${C_SRCS} PROPERTIES COMPILE_FLAGS 
    " -g -O0 -Wall")

if(WIN32)
    enable_language(RC)
    set(CMAKE_RC_COMPILE_OBJECT
        "<CMAKE_RC_COMPILER> ${RC_OPTIONS} -O coff -i <SOURCE> -o <OBJECT>")
endif(WIN32)



#{{{{ User Code 2
# Place your code here
#}}}}

add_executable(ssdv_demo ${RC_SRCS} ${CXX_SRCS} ${C_SRCS})
target_link_libraries(ssdv_demo ${LINK_OPTIONS})



#{{{{ User Code 3
# Place your code here
#install(TARGETS ${PROJECT_NAME} DESTINATION bin)
#}}}}

