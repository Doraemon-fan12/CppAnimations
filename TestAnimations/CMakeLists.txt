cmake_minimum_required(VERSION 3.10)
project(TestAnimations)

set(CMAKE_CXX_STANDARD 17)

# Set GLFW directory manually
set(CMAKE_PREFIX_PATH "/usr/lib/x86_64-linux-gnu/cmake")

# Find packages
find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)
find_package(glfw3 REQUIRED CONFIG)

# Include directories
include_directories(${GLEW_INCLUDE_DIRS} "/usr/include" "/usr/local/include")

# Add the executable
file(GLOB SOURCES "src/*.cpp")
add_executable(TestAnimations ${SOURCES})

# Link the libraries
target_link_libraries(TestAnimations ${OPENGL_LIBRARIES} ${GLEW_LIBRARIES} glfw)
