# CMakeList.txt: OpenGL 的 CMake 项目，在此处包括源代码并定义
# 项目特定的逻辑。
#
#cmake_minimum_required (VERSION 3.8)

#project ("OpenGL")

# 将源代码添加到此项目的可执行文件。
#add_executable (OpenGL "OpenGL.cpp" "OpenGL.h")

# TODO: 如有需要，请添加测试并安装目标。



cmake_minimum_required (VERSION 3.8)
project ("OpenGL")
include_directories(${PROJECT_SOURCE_DIR}/include)
link_directories(lib)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_DEBUG ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY_DEBUG ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG ${CMAKE_BINARY_DIR}/bin)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_RELEASE ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY_RELEASE ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_BINARY_DIR}/bin)
file(COPY "lib" DESTINATION ${CMAKE_BINARY_DIR})
file(GLOB_RECURSE  src_dir "./src/*.c" "./src/*.h" "./src/*.cpp" )
add_executable (OpenGL "OpenGL.cpp" "OpenGL.h" ${src_dir})
target_link_libraries(OpenGL glfw3  opengl32)
