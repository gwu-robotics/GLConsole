FIND_PACKAGE( GLUT REQUIRED )
FIND_PACKAGE( GLEW REQUIRED )
#FIND_PACKAGE( GLU REQUIRED )
FIND_PACKAGE( OpenGL REQUIRED )

IF( APPLE AND OPENGL_FOUND )
		ADD_DEFINITIONS( -DHAVE_APPLE_OPENGL_FRAMEWORK )
ENDIF( APPLE AND OPENGL_FOUND)

INCLUDE_DIRECTORIES( ${CMAKE_SOURCE_DIR} ${GLUT_INCLUDE_DIR} ${GLEW_INCLUDE_DIR} )
#LINK_DIRECTORIES( "../../CVars/" "../../GLConsole/" )
ADD_EXECUTABLE( GlutConsoleDemo GlutConsoleDemo.cpp )
TARGET_LINK_LIBRARIES( GlutConsoleDemo cvars ${GLUT_LIBRARIES} ${GLU_LIBRARIES} ${OPENGL_LIBRARIES} ${GLEW_LIBRARY} )

