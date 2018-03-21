cmake_minimum_required(VERSION 3.0)
project(ucat)

set(CMAKE_CXX_STANDARD 11)

add_compile_options(-Wall -g -fPIC -fno-exceptions -fno-rtti -fpermissive -Wno-sign-compare)
add_definitions(-D_DEBUG -DUTP_DEBUG_LOGGING -DPOSIX)

include_directories(${CMAKE_SOURCE_DIR})

add_executable(ucat
        ucat.c
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
