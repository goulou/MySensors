# Project name
project(MySensors_DallasTemperature_${DEVICE_NAME})

# CMake version
cmake_minimum_required(VERSION 2.6)

message("Including ${PROJECT_NAME} for arch : ${ARDUINO_ARCH}")

file(GLOB SRC_FILES_CPP ${CMAKE_CURRENT_SOURCE_DIR}/*.cpp)
file(GLOB SRC_FILES_C   ${CMAKE_CURRENT_SOURCE_DIR}/*.c)


add_library(${PROJECT_NAME} ${SRC_FILES_C} ${SRC_FILES_CPP})

target_include_directories(
	${PROJECT_NAME} PUBLIC
	${CMAKE_CURRENT_SOURCE_DIR}
	)
target_link_libraries(${PROJECT_NAME} MySensors_${DEVICE_NAME})
target_link_libraries(${PROJECT_NAME} MySensors_OneWire_${DEVICE_NAME})

