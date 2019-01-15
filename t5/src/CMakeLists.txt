add_executable(curltest main.c)

# method 1
# include_directories(/usr/include)
# target_link_libraries(curltest curl)

# method 2
find_package(CURL)
if(CURL_FOUND)
	include_directories(CURL_INCLUDE_DIR)
	target_link_libraries(curltest ${CURL_LIBRARY})
else(CURL_FOUND)
	message(FATAL_ERROR "curl library not fount")
endif(CURL_FOUND)
