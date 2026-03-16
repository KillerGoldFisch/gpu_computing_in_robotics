cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

project(GPU_Computing_in_Robotics_tutorial_lesson_5)

set_directory_properties( PROPERTIES COMPILE_DEFINITIONS "" )

include_directories(include)
include_directories(${PCL_INCLUDE_DIRS})
add_definitions(${PCL_DEFINITIONS})

cuda_add_executable(lesson_5
	src/lesson_5_main.cpp
	src/cudaWrapper.cpp
	src/lesson_5.cu
	src/cuda_SVD.cu
)
target_link_libraries(lesson_5
	${OPENGL_LIBRARIES}
	${GLUT_LIBRARIES}
	${PCL_LIBRARIES}
)
