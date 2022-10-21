cmake_minimum_required(VERSION 3.24)

set(CXX_FILES src/init.cpp)

add_library(lightbreath SHARED ${CXX_FILES})
target_include_directories(lightbreath PUBLIC ${Dragon_INCLUDE_DIRS})
target_link_libraries(lightbreath PUBLIC ${Dragon_LINK_LIBRARIES})
add_library(Dragon::Lightbreath ALIAS lightbreath)