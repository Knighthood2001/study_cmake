cmake_minimum_required (VERSION 3.5)

project (demo06)

set (SRC_LIST ${PROJECT_SOURCE_DIR}/testFunc/testFunc.c)

add_library (testFunc_shared SHARED ${SRC_LIST})
add_library (testFunc_static STATIC ${SRC_LIST})

set_target_properties (testFunc_shared PROPERTIES OUTPUT_NAME "testFunc")
set_target_properties (testFunc_static PROPERTIES OUTPUT_NAME "testFunc")

set (LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)

# 这里又出现了新的命令和预定义变量:
# add_library: 生成动态库或静态库(第1个参数指定库的名字；第2个参数决定是动态还是静态，如果没有就默认静态；第3个参数指定生成库的源文件)
# set_target_properties: 设置最终生成的库的名称，还有其它功能，如设置库的版本号等
# LIBRARY_OUTPUT_PATH: 库文件的默认输出路径，这里设置为工程目录下的lib目录

# PS：前面使用set_target_properties重新定义了库的输出名称，如果不使用set_target_properties也可以，那么库的名称就是add_library里定义的名称，
# 只是连续2次使用add_library指定库名称时（第一个参数），这个名称不能相同，而set_target_properties可以把名称设置为相同，只是最终生成的库文件后缀不同
# （一个是.so，一个是.a），这样相对来说会好看点。