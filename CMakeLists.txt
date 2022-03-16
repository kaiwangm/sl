cmake_minimum_required(VERSION 3.22)
project(sl 
    VERSION 0.0.1
    DESCRIPTION "sl"
    LANGUAGES C
)

add_executable(sl sl.c)

add_library(libPDCurses STATIC IMPORTED)
set_target_properties(libPDCurses PROPERTIES IMPORTED_LOCATION ${CMAKE_CURRENT_SOURCE_DIR}/pdcurses/pdcurses.lib)

target_link_libraries(sl libPDCurses)