# CMakeList.txt : CMake project for ImGuiExample, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

# Add source to this project's executable.
add_executable (ImGuiExample "ImGuiExample.cpp"  "UseImGui.cpp" "UseImGui.h")

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET ImGuiExample PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.
find_package(imgui CONFIG REQUIRED)
target_link_libraries(ImGuiExample PRIVATE imgui::imgui)

find_package(glfw3 CONFIG REQUIRED)
target_link_libraries(ImGuiExample PRIVATE glfw)

find_package(glad CONFIG REQUIRED)
target_link_libraries(ImGuiExample PRIVATE glad::glad)