cmake_minimum_required(VERSION 3.1)

project(cimgui_nodes)

add_library(cimgui_nodes STATIC)

target_sources(cimgui_nodes PRIVATE 
    cimgui_nodes.cpp
    nodes/nodes.h
    nodes/nodes.cpp
)

set(CMAKE_CXX_STANDARD 11)

target_compile_definitions(cimgui_nodes PUBLIC IMGUI_DISABLE_OBSOLETE_FUNCTIONS=1)
target_compile_definitions(cimgui_nodes PUBLIC IMGUINODES_NAMESPACE=imguinodes)
target_compile_definitions(cimgui_nodes PUBLIC IMGUI_DEFINE_MATH_OPERATORS)

target_link_libraries(cimgui_nodes PRIVATE cimgui)

target_include_directories(cimgui_nodes PUBLIC nodes)
target_include_directories(cimgui_nodes PUBLIC ../cimgui/imgui)
target_include_directories(cimgui_nodes PUBLIC ../cimgui)
