cmake_minimum_required (VERSION 2.8)

project (demo03)

aux_source_directory(. SRC_LIST)

add_executable(main ${SRC_LIST})


# cmake_minimum_required (VERSION 2.8)

# project (demo)

# set( SRC_LIST
# 	 ./main.c
# 	 ./testFunc1.c
# 	 ./testFunc.c)

# add_executable(main ${SRC_LIST})