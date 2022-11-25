cmake_minimum_required(VERSION 3.10)
project(prj CXX)

set(CMAKE_BUILD_TYPE DEBUG)
set(CMAKE_VERBOSE_MAKEFILE TRUE)

add_executable(${PROJECT_NAME} main.cpp)
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 20)

if (LINUX)
	find_package(SFML 2.5 COMPONENTS audio window graphics REQUIRED)
endif()

#[[get_cmake_property(_variableNames VARIABLES)
foreach(_variableName ${_variableNames})
	message(STATUS "${_variableName}=${${_variableName}}")
endforeach()]]


if (UNIX)
	message(STATUS "Targetting")
	target_link_libraries(${PROJECT_NAME} sfml-window sfml-system sfml-graphics sfml-audio)
endif()


#[[
target_include_directories(${PROJECT_NAME} PRIVATE folders....) 

Avoid target_include_directories and prefer find_library() 

Avoid target_include_directories and prefer find_library() 



]] 
