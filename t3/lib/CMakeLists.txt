cmake_minimum_required(VERSION 2.8)

set(LIBHELLO_SRC hello.c)

add_library(hello_shared SHARED ${LIBHELLO_SRC})
add_library(hello_static STATIC ${LIBHELLO_SRC})

set_target_properties(hello_shared PROPERTIES OUTPUT_NAME "hello")
set_target_properties(hello_static PROPERTIES OUTPUT_NAME "hello")

set(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/mylib)

install (TARGETS hello_shared hello_static
		LIBRARY DESTINATION libs
		ARCHIVE DESTINATION libs)

install(FILES hello.h DESTINATION include/hello)
