#SET(LIBRARY_OUTPUT_PATH ../../../lib/)
#IF(APPLE)
#    SET(LIBRARY_MODE_TARGET "MODULE")
#ELSE(APPLE)
#    SET(LIBRARY_MODE_TARGET "SHARED")
#ENDIF(APPLE)
#ADD_LIBRARY(routing ${LIBRARY_MODE_TARGET} astar.c astar_boost_wrapper.cpp)
#INSTALL(TARGETS routing DESTINATION ${LIBRARY_INSTALL_PATH})
#IF(APPLE)
#    SET_TARGET_PROPERTIES(routing PROPERTIES LINK_FLAGS "-bundle_loader ${POSTGRESQL_EXECUTABLE} -bundle")
#ENDIF(APPLE)

ADD_LIBRARY(astar OBJECT astar.c astar_boost_wrapper.cpp)
