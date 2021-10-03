cmake_minimum_required(VERSION 3.10)

if (${CMAKE_SOURCE_DIR} MATCHES ${CMAKE_BINARY_DIR})
	message(FATAL_ERROR "Prevented in-tree build")
endif ()

project(mpgx 
	VERSION 0.1.0
	DESCRIPTION "Multi-platform graphics library"
	HOMEPAGE_URL "https://github.com/cfnptr/mpgx"
	LANGUAGES C)

set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED TRUE)

add_library(glad STATIC
	src/glad/glad.c)
target_include_directories(mpgx PUBLIC
	${PROJECT_BINARY_DIR}
	${PROJECT_SOURCE_DIR}/include)
