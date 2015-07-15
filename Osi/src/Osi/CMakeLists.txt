file(
	GLOB
	OSI_OSI_HEADER
	*.hpp
	*.h
)
file(
	GLOB
	OSI_OSI_CPP
	*.cpp
)

#ADD_LIBRARY(lib_Osi ${OSI_OSI_HEADER} ${OSI_OSI_CPP})
yong_add_library(Osi
  SOURCES ${OSI_OSI_HEADER} ${OSI_OSI_CPP}
  LIB_TYPE STATIC)
yong_install_header_files(osi_clp "" ${OSI_OSI_HEADER})
yong_add_library_end(Osi)
