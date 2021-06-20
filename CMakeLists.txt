cmake_minimum_required(VERSION 3.9)

add_library(pthread SHARED IMPORTED GLOBAL)

set(LIB_SUBDIR "win_x64")
if(CMAKE_SIZEOF_VOID_P EQUAL 4)
    set(LIB_SUBDIR "win_x86")
endif()

set_target_properties(pthread PROPERTIES INTERFACE_INCLUDE_DIRECTORIES ${CMAKE_CURRENT_LIST_DIR}/include)
set_target_properties(pthread PROPERTIES IMPORTED_LOCATION ${CMAKE_CURRENT_LIST_DIR}/dll/${LIB_SUBDIR}/pthreadVC2.dll)
set_target_properties(pthread PROPERTIES IMPORTED_IMPLIB ${CMAKE_CURRENT_LIST_DIR}/lib/${LIB_SUBDIR}/pthreadVC2.lib)
