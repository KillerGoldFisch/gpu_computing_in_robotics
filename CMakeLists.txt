cmake_minimum_required(VERSION 3.20.0 FATAL_ERROR)


set(CMAKE_POLICY_VERSION_MINIMUM 3.5)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_C_COMPILER gcc)
set(CMAKE_CXX_COMPILER g++)
set(CUDA_COMPILER /usr/local/cuda/bin/nvcc)

set(CUDA_NVCC_FLAGS "
    -gencode arch=compute_80,code=sm_80 
    -gencode arch=compute_86,code=sm_86 
    -gencode arch=compute_89,code=sm_89 
    -gencode arch=compute_90,code=sm_90 
    -gencode arch=compute_100,code=sm_100 
    -gencode arch=compute_103,code=sm_103 
    -gencode arch=compute_120,code=sm_120 
    -gencode arch=compute_121,code=sm_121 
    -allow-unsupported-compiler 
    --expt-relaxed-constexpr 
    -D_FORCE_INLINES")

project(GPU_Computing_in_Robotics)

find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)
find_package(PCL REQUIRED)
find_package(CUDA REQUIRED)
find_package(OpenCV REQUIRED)

add_subdirectory(tutorial/lesson_0)
add_subdirectory(tutorial/lesson_1)
add_subdirectory(tutorial/lesson_2)
add_subdirectory(tutorial/lesson_3)
add_subdirectory(tutorial/lesson_4)
add_subdirectory(tutorial/lesson_5)
add_subdirectory(tutorial/lesson_6)
add_subdirectory(tutorial/lesson_7)
add_subdirectory(tutorial/lesson_8)
add_subdirectory(tutorial/lesson_9)
add_subdirectory(tutorial/lesson_10)
add_subdirectory(tutorial/lesson_11)
add_subdirectory(tutorial/lesson_12)
add_subdirectory(tutorial/lesson_13)
add_subdirectory(tutorial/lesson_14)
add_subdirectory(tutorial/lesson_15)
add_subdirectory(tutorial/lesson_16)
add_subdirectory(tutorial/lesson_17)
#  add_subdirectory(tutorial/lesson_18) //  Uses deprecated CUDA calls, needs to be updated
add_subdirectory(tutorial/lesson_19)

add_subdirectory(use_cases/fastSLAM)
add_subdirectory(use_cases/particle_filter_localization)
add_subdirectory(use_cases/robotic_arm_collision_detection)