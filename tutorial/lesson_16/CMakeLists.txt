cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

project(gpu_computing_in_robotics_lesson_16) 

set_directory_properties( PROPERTIES COMPILE_DEFINITIONS "" )

include_directories(include)
include_directories(${PCL_INCLUDE_DIRS})
add_definitions(${PCL_DEFINITIONS})

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fopenmp")

cuda_add_executable(lesson_16
	src/lesson_16_main.cpp
	src/cudaWrapper.cpp
	src/lesson_16.cu
	src/data_model.cpp
	src/CCUDAAXBSolverWrapper.cpp
)
target_link_libraries(lesson_16
	${OPENGL_LIBRARIES}
	${GLUT_LIBRARIES}
	${PCL_LIBRARIES}
	${CUDA_cusparse_LIBRARY}
	${CUDA_cusolver_LIBRARY}
	${CUDA_cublas_LIBRARY}
)



