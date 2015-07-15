file(
	GLOB_RECURSE
	OSI_HEADERS
	*.hpp
	*.h
)
file(
	GLOB_RECURSE
	OSI_SRCS
	*.cpp
)
#ADD_LIBRARY(lib_OsiClpSolver ${OSI_HEADERS} ${OSI_SRCS})
yong_add_library(OsiClpSolver
  SOURCES ${OSI_HEADERS} ${OSI_SRCS}
  LIB_TYPE STATIC)
yong_install_header_files(osi_clp "" ${OSI_HEADERS})
yong_add_library_end(OsiClpSolver)
