# min required cmake version
cmake_minimum_required(VERSION 3.19.2)

# project name
project(hello_cmake)

# set source folders
set(SOURCE 
    main.cpp 
    src/calc.cpp
)

# set include folders
set(INCLUDE
    include
    lib
)

# print source
message(WARNING "SOURCE: ${SOURCE}")

# print CMAKE_SOURCE_DIR
message("PATH: " ${CMAKE_SOURCE_DIR})

# if else condition checks if main.cpp exists
if(EXISTS ${CMAKE_SOURCE_DIR}/main.cpp)
    message("main.cpp exists.")
else()
    message(FATAL_ERROR "main.cpp does not exist.")
endif()

# executable name + source files
add_executable(hello_binary ${SOURCE})

# include directory
target_include_directories(hello_binary PUBLIC ${INCLUDE})

# add cmake list in lib subdirectory
add_subdirectory(${CMAKE_SOURCE_DIR}/lib)

# link wifi library to executable given
target_link_libraries(hello_binary PUBLIC wifi_lib )
