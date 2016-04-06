add_executable(SimplePuppets SimplePuppets.cpp)

# Local libraries
include_directories(${CLM_SOURCE_DIR}/include)

include_directories(../../lib/local/CLM/include)
include_directories(../../lib/local/FaceAnalyser/include)

target_link_libraries(SimplePuppets CLM)
target_link_libraries(SimplePuppets FaceAnalyser)
target_link_libraries(SimplePuppets dlib)

if(WIN32)
	target_link_libraries(SimplePuppets ${OpenCVLibraries})
endif(WIN32)
if(UNIX)
    target_link_libraries(SimplePuppets ${OpenCV_LIBS} ${Boost_LIBRARIES} ${TBB_LIBRARIES})
endif(UNIX)

install (TARGETS SimplePuppets DESTINATION ${CMAKE_BINARY_DIR}/bin)
