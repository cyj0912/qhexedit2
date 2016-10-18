cmake_minimum_required(VERSION 3.0)
project(qhexedit)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
find_package(Qt5Widgets)

file(GLOB SOURCE . *.cpp *.h)
add_library(qhexedit2 SHARED ${SOURCE})

target_link_libraries(qhexedit2 Qt5::Widgets)
if(WIN32)
	set_target_properties(qhexedit2 PROPERTIES WINDOWS_EXPORT_ALL_SYMBOLS 1)
endif()
