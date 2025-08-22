cmake_minimum_required(VERSION 3.16)
project(M12_List_Stack)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

file(GLOB ALL_SOURCES "*.cpp")

if(DEFINED SOURCE_FILE)
    get_filename_component(EXEC_NAME "${SOURCE_FILE}" NAME_WE)
    string(REPLACE " " "_" EXEC_NAME "${EXEC_NAME}")
    message(STATUS "Building single file: ${SOURCE_FILE} → ${EXEC_NAME}")
    add_executable(${EXEC_NAME} ${SOURCE_FILE})
else()
    message(STATUS "Building full project with sources: ${ALL_SOURCES}")
    add_executable(${PROJECT_NAME} ${ALL_SOURCES})
endif()