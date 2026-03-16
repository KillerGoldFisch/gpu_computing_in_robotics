cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

project(GPU_Computing_in_Robotics_tutorial_lesson_17)

set_directory_properties( PROPERTIES COMPILE_DEFINITIONS "" )

include_directories(include)

cuda_add_executable(lesson_17
	src/lesson_17_main.cpp
	src/cudaWrapper.cpp
	src/lesson_17.cu
)
target_link_libraries(lesson_17
	${OPENGL_LIBRARIES}
	${GLUT_LIBRARIES}
	${PCL_LIBRARIES}
)
