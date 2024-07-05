include(pimoroni_i2c.cmake)
include(pimoroni_bus.cmake)

set(LIB_NAME unicode_sorta)

if(NOT TARGET ${LIB_NAME})
	add_library(${LIB_NAME} INTERFACE)

	target_sources(${LIB_NAME} INTERFACE
	  ${CMAKE_CURRENT_LIST_DIR}/${LIB_NAME}.hpp
	)

	target_include_directories(${LIB_NAME} INTERFACE ${CMAKE_CURRENT_LIST_DIR})
endif()