cmake_minimum_required(VERSION 3.15)
PROJECT(FileServer)
SET(CMAKE_CXX_STANDARD 17)
include_directories(message)
add_subdirectory(event)
add_subdirectory(fileserver)
add_subdirectory(threadpool)
add_subdirectory(timer)
add_subdirectory(utils)
add_executable(FileServer main.cpp)

target_link_libraries(${PROJECT_NAME}
        PUBLIC
        fileserver
        threadpool
        event
        timer
        utils
)

