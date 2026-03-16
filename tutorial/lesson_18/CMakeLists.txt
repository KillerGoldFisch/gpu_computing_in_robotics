cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

project(GPU_Computing_in_Robotics_tutorial_lesson_18)

set_directory_properties( PROPERTIES COMPILE_DEFINITIONS "" )

include_directories(include)

cuda_add_executable(lesson_18
	src/lesson_18_main.cpp
	src/CUDA.cu
	src/GPUMatching.cpp
	src/BFROSTMatcher.cpp
	
)
target_link_libraries(lesson_18
	${OPENGL_LIBRARIES}
	${GLUT_LIBRARIES}
	${PCL_LIBRARIES}
	${OpenCV_LIBS}
)
