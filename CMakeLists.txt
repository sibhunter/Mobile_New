cmake_minimum_required(VERSION 3.0)
project(MyProject)

find_package(PkgConfig REQUIRED)
pkg_check_modules(ZMQ REQUIRED libzmq)

include_directories(${ZMQ_INCLUDE_DIRS})
link_directories(${ZMQ_LIBRARY_DIRS})

add_executable(server src/server.c)
target_link_libraries(server ${ZMQ_LIBRARIES})

add_executable(client src/client.c)
target_link_libraries(client ${ZMQ_LIBRARIES})
