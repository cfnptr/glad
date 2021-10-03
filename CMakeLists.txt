cmake_minimum_required(VERSION 3.10)

if (${CMAKE_SOURCE_DIR} MATCHES ${CMAKE_BINARY_DIR})
	message(FATAL_ERROR "Prevented in-tree build")
endif ()

project(glad
	VERSION 0.1.32
	DESCRIPTION "Multi-Language GL/GLES/EGL/GLX/WGL Loader-Generator based on the official specs."
	HOMEPAGE_URL "https://glad.dav1d.de"
	LANGUAGES C)

set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED TRUE)

add_library(glad STATIC
	src/glad.c)
target_include_directories(glad PUBLIC
	${PROJECT_BINARY_DIR}
	${PROJECT_SOURCE_DIR}/include)
