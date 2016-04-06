add_executable(ConsolePuppets ConsolePuppets.cpp)

# Local libraries
include_directories(${CLM_SOURCE_DIR}/include)

include_directories(../../lib/local/CLM/include)
include_directories(../../lib/local/FaceAnalyser/include)
include_directories(../../lib/local/Puppets/include)
			
target_link_libraries(ConsolePuppets CLM)
target_link_libraries(ConsolePuppets FaceAnalyser)
target_link_libraries(ConsolePuppets Puppets)
target_link_libraries(ConsolePuppets dlib)

if(WIN32)
	target_link_libraries(ConsolePuppets ${OpenCVLibraries})
endif(WIN32)
if(UNIX)
    target_link_libraries(ConsolePuppets ${OpenCV_LIBS} ${Boost_LIBRARIES} ${TBB_LIBRARIES} ${OPENGL_LIBRARIES} ${GLUT_LIBRARY})
endif(UNIX)

install (TARGETS ConsolePuppets DESTINATION ${CMAKE_BINARY_DIR}/bin)
