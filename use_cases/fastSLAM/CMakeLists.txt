cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

project(fastSLAM)

set_directory_properties( PROPERTIES COMPILE_DEFINITIONS "" )

include_directories( include )	
include_directories(${PCL_INCLUDE_DIRS})
add_definitions(${PCL_DEFINITIONS})

SET(COMMON_SOURCES
	../../use_cases/common/src/data_model.cpp
)

include_directories(../common/include)

cuda_add_executable(fastSLAM
  	src/fastSLAM.cpp
  	src/rgd_particle_filter_CUDAWrapper.cpp
 	src/cuda_algorithms.cu
  	${COMMON_SOURCES}
  )
target_link_libraries(fastSLAM
	${OPENGL_LIBRARIES} 
	${GLUT_LIBRARIES}
	${PCL_LIBRARIES}
)


