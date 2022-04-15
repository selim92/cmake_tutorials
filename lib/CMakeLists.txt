cmake_minimum_required(VERSION 3.19.2)

message(STATUS "Added cmake from lib")

#make library from wifi module
add_library(wifi_lib
    wifi.cpp
    wifi.hpp
)