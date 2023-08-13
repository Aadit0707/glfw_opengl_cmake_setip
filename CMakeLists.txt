
cmake_minimum_required(VERSION 3.12)




enable_language(CXX)
project(Test VERSION 1.0.0)



add_library(
    glad  
    glad.c
    glad.h
    KHR/khrplatform.h
)


add_subdirectory(libs/glfw)
include_directories(glfw/include)
add_executable(${PROJECT_NAME} main.cpp
)

target_link_libraries(${PROJECT_NAME}  glfw ${GLFW_LIBRARIES} glad )

