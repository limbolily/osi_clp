
file(
	GLOB
	COINUTILS_HEADER
	*.hpp
	*.h
)
file(
	GLOB
	COINUTILS_CPP
	*.cpp
)


#ADD_LIBRARY(lib_CoinUtils ${COINUTILS_HEADER} ${COINUTILS_CPP})
yong_add_library(CoinUtils
  SOURCES ${COINUTILS_HEADER} ${COINUTILS_CPP}
  LIB_TYPE STATIC)
yong_install_header_files(osi_clp "" ${COINUTILS_HEADER})
yong_add_library_end(CoinUtils)

