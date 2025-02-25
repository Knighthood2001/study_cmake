cmake_minimum_required (VERSION 2.8)

project (demo04)

include_directories (testFunc testFunc1)

aux_source_directory (testFunc SRC_LIST)
aux_source_directory (testFunc1 SRC_LIST1)

add_executable (main main.c ${SRC_LIST} ${SRC_LIST1})