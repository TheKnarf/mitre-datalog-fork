cmake_minimum_required(VERSION 3.10.2)

add_executable(bin2c bin2c.c)

find_package(Lua REQUIRED)

add_custom_command(
  OUTPUT  ${CMAKE_BINARY_DIR}/dl_lua.h
  COMMAND bin2c -o ${CMAKE_BINARY_DIR}/dl_lua.h datalog.lua.in
  DEPENDS datalog.lua.in
  WORKING_DIRECTORY ${CMAKE_SOURCE_DIR}/src
)

add_executable(datalog
	datalog.c
	interp.c
	loader.c
	${CMAKE_BINARY_DIR}/dl_lua.h
	)

target_include_directories(datalog PUBLIC
	../include
	${CMAKE_BINARY_DIR}
	${LUA_INCLUDE_DIR}
	)

target_link_libraries(datalog
	${LUA_LIBRARIES}
	)