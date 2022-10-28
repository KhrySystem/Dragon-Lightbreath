cmake_minimum_required(VERSION 3.20)

set(CXX_FILES src/init.cpp)

if(DRAGON_BUILD_SHARED)
	add_library(lightbreath SHARED ${CXX_FILES})
else() 
	add_library(lightbreath STATIC ${CXX_FILES})
endif()
target_include_directories(lightbreath PUBLIC ${Dragon_INCLUDE_DIRS})
target_link_libraries(lightbreath PUBLIC ${Boost_LIBRARIES})
add_library(Dragon::Lightbreath ALIAS lightbreath)