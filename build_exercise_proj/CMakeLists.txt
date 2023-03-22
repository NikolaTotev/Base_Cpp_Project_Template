cmake_minimum_required(VERSION 3.10)

project(
    build_exercise_proj 
    LANGUAGES CXX
    VERSION 1.0.0
)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON) 

set(_INC_FOLDER_NAME include) 
set(_INC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/${_INC_FOLDER_NAME}) 

set(_HEADER_DIR ${_INC_DIR}/${PROJECT_NAME}) 
set(_SRC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src) 


add_executable( 
    ${PROJECT_NAME}      
        ${_HEADER_DIR}/header.hpp

        ${_SRC_DIR}/main.cpp 
)

set_target_properties(
    ${PROJECT_NAME}
    PROPERTIES
        CXX_STANDARD 20
        CXX_STANDARD_REQUIRED YES
        CXX_EXTENSIONS NO
)

target_link_libraries(${PROJECT_NAME} PRIVATE tools_lib_proj)
target_include_directories(${PROJECT_NAME} PRIVATE ${_INC_DIR})

add_subdirectory(libs)