cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

project(GPU_Computing_in_Robotics_use_cases_robotic_arm_collision_detection) 

set_directory_properties( PROPERTIES COMPILE_DEFINITIONS "" )

include_directories(include)
include_directories(${PCL_INCLUDE_DIRS})
add_definitions(${PCL_DEFINITIONS})

cuda_add_executable(robotic_arm_collision_detection_main
	src/robotic_arm_collision_detection_main.cpp
	src/cudaWrapper.cpp
	src/lesson_3.cu
)
target_link_libraries(robotic_arm_collision_detection_main
	${OPENGL_LIBRARIES} 
	${GLUT_LIBRARIES}
	${PCL_LIBRARIES}
)
