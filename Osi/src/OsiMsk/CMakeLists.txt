file(
	GLOB
	OsiMskSolverInterface_CPP
	*.cpp
)

file(
	GLOB
	OsiMskSolverInterface_HEADER
	*.hpp
	*.h
)

IF (EXISTS "${MOSEK_INCLUDE}" AND EXISTS "${MOSEK_LIB}")
  INCLUDE_DIRECTORIES( ${MOSEK_INCLUDE} )
  #ADD_LIBRARY(lib_Osi_Msk ${OsiMskSolverInterface_CPP}  ${OsiMskSolverInterface_HEADER})
  yong_add_library(Osi_Msk
    SOURCES ${OsiMskSolverInterface_CPP} ${OsiMskSolverInterface_HEADER}
    LIB_TYPE STATIC)
  yong_install_header_files(osi_clp "" ${OsiMskSolverInterface_HEADER})
  yong_add_library_end(Osi_Msk)
ENDIF (EXISTS "${MOSEK_INCLUDE}" AND EXISTS "${MOSEK_LIB}")
