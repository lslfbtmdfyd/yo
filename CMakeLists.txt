cmake_minimum_required (VERSION 3.5)

project (pub_mqtt_demo)


include_directories(${CMAKE_CURRENT_SOURCE_DIR}/open62541/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/open62541/src_generated)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/open62541/plugins)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/open62541/plugins/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/open62541/arch)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/open62541/deps)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/open62541/src)

find_library(OPEN62541_LIB libopen62541.a HINTS ${CMAKE_CURRENT_SOURCE_DIR}/open62541/)


add_executable(mqtt_pub ${CMAKE_CURRENT_SOURCE_DIR}/src/tutorial_pubsub_mqtt_publish.c)
target_link_libraries(mqtt_pub ${OPEN62541_LIB} pthread)
