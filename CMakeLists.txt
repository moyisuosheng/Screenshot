cmake_minimum_required(VERSION 3.5)

project(Screenshot)

set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "GLFW lib only")
set(GLFW_BUILD_TESTS OFF CACHE BOOL "GLFW lib only")
set(GLFW_BUILD_DOCS OFF CACHE BOOL "GLFW lib only")
set(GLFW_BUILD_INSTALL OFF CACHE BOOL "GLFW lib only")
add_subdirectory(vendor/glfw)

set(CPP_FILES vendor/imgui/imgui.cpp
        vendor/imgui/imgui_impl_glfw.cpp
        vendor/imgui/imgui_impl_opengl3.cpp
        vendor/imgui/imgui.cpp
        vendor/imgui/imgui_tables.cpp
        vendor/imgui/imgui_widgets.cpp
        vendor/imgui/imgui_demo.cpp
        vendor/imgui/imgui_draw.cpp
)

add_executable(${PROJECT_NAME} src/win/main.cpp ${CPP_FILES})

target_link_libraries(${PROJECT_NAME} glfw opengl32 ${OPENGL_LIBRARIES} ${GLFW_LIBRARIES})
