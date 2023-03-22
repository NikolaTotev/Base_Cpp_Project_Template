cmake_minimum_required(VERSION 3.10)

project(
    tools_lib_proj
    LANGUAGES CXX
    VERSION 1.0.0
)

set(_INC_FOLDER_NAME include) 
set(_INC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/${_INC_FOLDER_NAME}) 

set(_HEADER_DIR ${_INC_DIR}/${PROJECT_NAME}) 
set(_SRC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src) 


add_library(
    ${PROJECT_NAME} 
        STATIC 
            ${_HEADER_DIR}/tools.hpp

            ${_SRC_DIR}/tools.cpp
)

set_target_properties(
    ${PROJECT_NAME}
    PROPERTIES
        CXX_STANDARD 20
        CXX_STANDARD_REQUIRED YES
        CXX_EXTENSIONS NO
)

target_include_directories(${PROJECT_NAME} PUBLIC ${_INC_DIR})