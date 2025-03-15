cmake_minimum_required( VERSION 3.30 )

project( askii 
    LANGUAGES C CXX
    VERSION 0.1.0
    DESCRIPTION ""
)

include( FindCurses )
include_directories( ${CURSES_INCLUDE_DIR} )

set( CURSES_NEED_NCURSES TRUE )
add_definitions( -DNCURSES_STATIC )

add_executable( askii 
    askii.h askii.c
    config.h
    graphics.h graphics.c
    list.h list.c
    types.h
    util.h util.c
)

target_link_libraries( askii ${CURSES_LIBRARIES} )
