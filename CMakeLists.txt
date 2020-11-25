cmake_minimum_required(VERSION 3.19)

project(imgui CXX)

add_library(imgui INTERFACE)
target_compile_definitions(imgui INTERFACE GLM_FORCE_CXX17)
target_include_directories(imgui SYSTEM INTERFACE "./")

#add_library(imgui STATIC ${imgui_sources})
#source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${imgui_sources})
#target_include_directories(framework PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
#imgui\misc\single_file