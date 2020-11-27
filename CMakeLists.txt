cmake_minimum_required(VERSION 3.19)

project(imgui CXX)

option(USE_GLAD "Use glad as gl loader" YES)

# set up imgui submodule
set(imgui_sources
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_widgets.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_demo.cpp    
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_draw.cpp    
    ${CMAKE_CURRENT_SOURCE_DIR}/examples/imgui_impl_glfw.cpp    
    ${CMAKE_CURRENT_SOURCE_DIR}/examples/imgui_impl_opengl3.cpp    
)

message(STATUS "Initialising imgui library with sources:")

foreach(item IN LISTS imgui_sources)
    message(STATUS "${item}")
endforeach()

add_library(imgui STATIC ${imgui_sources})
source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${imgui_sources})

set_target_properties(imgui PROPERTIES FOLDER "Dependencies")

target_include_directories(imgui PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

#target_include_directories(imgui  ${imgui_sources})

#add_library(imgui STATIC ${imgui_sources})
