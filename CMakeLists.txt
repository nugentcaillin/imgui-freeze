cmake_minimum_required(VERSION 3.28)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

project(ImGuiFreeze)

add_subdirectory(extern/SDL)

add_executable(ImGuiFreeze
    extern/imgui/backends/imgui_impl_sdl3.cpp
    extern/imgui/backends/imgui_impl_sdlgpu3.cpp
    extern/imgui/imgui_demo.cpp
    extern/imgui/imgui_draw.cpp
    extern/imgui/imgui_tables.cpp
    extern/imgui/imgui_widgets.cpp
    extern/imgui/imgui.cpp
    extern/imgui/examples/example_sdl3_sdlgpu3/main.cpp
)

target_link_libraries(ImGuiFreeze
    SDL3::SDL3
)

target_include_directories(ImGuiFreeze
    PUBLIC
        "${CMAKE_CURRENT_SOURCE_DIR}/extern/imgui" 
        "${CMAKE_CURRENT_SOURCE_DIR}/extern/imgui/backends" 
)