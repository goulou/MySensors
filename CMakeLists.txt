# Project name
project(MySensors_${DEVICE_NAME})

# CMake version
cmake_minimum_required(VERSION 2.6)

message("Including ${PROJECT_NAME} for arch : ${ARDUINO_ARCH}")

add_library(${PROJECT_NAME} INTERFACE)


target_include_directories(
	${PROJECT_NAME} INTERFACE
	${CMAKE_CURRENT_SOURCE_DIR}
	)
target_include_directories(
	${PROJECT_NAME} INTERFACE
	${CMAKE_CURRENT_SOURCE_DIR}/core
	)
target_link_libraries(${PROJECT_NAME} INTERFACE Arduino_${DEVICE_NAME})

