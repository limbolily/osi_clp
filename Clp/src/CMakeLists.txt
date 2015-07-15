file(
	GLOB
	CLP_SRC_HEADER
	*.hpp
	*.h
)
file(
	GLOB
	CLP_SRC_CPP
	*.cpp
)


file(
     GLOB
     REMOVE_CPP
     ClpCholeskyMumps.cpp
     ClpCholeskyUfl.cpp
     ClpCholeskyWssmp.cpp
     ClpCholeskyWssmpKKT.cpp
     *Abc*.cpp
)   

file(
     GLOB
    REMOVE_HEADER
     ClpCholeskyMumps.hpp
     ClpCholeskyUfl.hpp
     ClpCholeskyWssmp.hpp
     ClpCholeskyWssmpKKT.hpp 
     *Abc*.hpp
     *Abc*.h
)   

list(REMOVE_ITEM CLP_SRC_HEADER ${REMOVE_HEADER})
list(REMOVE_ITEM CLP_SRC_CPP ${REMOVE_CPP})

#ADD_LIBRARY(lib_clp ${CLP_SRC_HEADER} ${CLP_SRC_CPP})
yong_add_library(clp
  SOURCES ${CLP_SRC_HEADER} ${CLP_SRC_CPP}
  LIB_TYPE STATIC)
#TARGET_LINK_LIBRARIES(lib_clp lib_CoinUtils )
yong_add_dependence(osi_clp clp
  DEPENDENT_LOCAL_LIBS CoinUtils)
yong_install_header_files(osi_clp "" ${CLP_SRC_HEADER})
yong_add_library_end(clp)

add_subdirectory(OsiClp)


