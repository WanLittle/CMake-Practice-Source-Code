cmake_minimum_required(VERSION 2.8)

add_executable(main main.c)

include_directories(../include/hello)

target_link_libraries(main ../../lib/hello)
