include_directories(${BOOST_INCLUDE_DIR})

SET(SOURCE
        src/Avatar.cc
)

SET(HEADERS
        include/Avatar.h
)

include_directories(./include)
include_directories(${PUPPETS_SOURCE_DIR}/include)
include_directories(../CLM/include)

add_library(Puppets ${SOURCE} ${HEADERS})

install (TARGETS Puppets DESTINATION bin)
install (FILES HEADERS DESTINATION include)
