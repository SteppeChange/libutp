cmake_minimum_required(VERSION 3.0)
project(utp)

set(CMAKE_CXX_STANDARD 11)

add_compile_options(-Wall -g -fPIC -fno-exceptions -fno-rtti -fpermissive -Wno-sign-compare)
#add_definitions(-D_DEBUG -DUTP_DEBUG_LOGGING -DPOSIX)

include_directories(${CMAKE_SOURCE_DIR})

set(SOURCE_FILES
        utp.h
        utp_api.cpp
        utp_callbacks.cpp
        utp_callbacks.h
        utp_hash.cpp
        utp_hash.h
        utp_internal.cpp
        utp_internal.h
        utp_packedsockaddr.cpp
        utp_packedsockaddr.h
        utp_templates.h
        utp_types.h
        utp_utils.cpp
        utp_utils.h)

set(SOURCE_FILES_UCAT
        ${SOURCE_FILES}
        ucat.c)

add_executable(ucat ${SOURCE_FILES_UCAT})
add_library(utp ${SOURCE_FILES})



