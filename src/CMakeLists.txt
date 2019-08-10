cmake_minimum_required(VERSION 3.5)

project(LearnOpenGL)

set(target LearnOpenGL)

include_directories(../third_party/glfw3.3/include)
include_directories(../third_party/glad/include)
include_directories(../third_party/glm-0.9.9.5)
link_directories(${CMAKE_CURRENT_LIST_DIR}/../third_party/glfw3.3/lib-vc2015)

file(GLOB ${target}_HEADERS
	shader.h
	stb_image.h
)

file(GLOB ${target}_SRCS
	glad.c
	main.cpp
)

source_group("Header Files" FILES ${${target}_HEADERS})
source_group("Source Files" FILES ${${target}_SRCS})

add_executable(${target}
	${${target}_HEADERS}
	${${target}_SRCS}
)

target_link_libraries(${target} glfw3.lib)
target_link_libraries(${target} opengl32.lib)