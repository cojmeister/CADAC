cmake_minimum_required(VERSION 3.10)

# Project name (you can change this to match your project)
project(GHAME3 CXX)

# Set C++ standard (adjust as needed)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Find source files automatically
file(GLOB SOURCES
        "*.cpp"
)

# Create executable from all source files
add_executable(${PROJECT_NAME} ${SOURCES})

# Optional: Include directories if you have any additional include paths
# target_include_directories(${PROJECT_NAME} PRIVATE
#     ${CMAKE_CURRENT_SOURCE_DIR}
# )

# Optional: Link libraries if needed
# target_link_libraries(${PROJECT_NAME}
#     some_library
# )

# Optional: Compiler-specific optimizations
if(MSVC)
    target_compile_options(${PROJECT_NAME} PRIVATE /W4)
else()
    target_compile_options(${PROJECT_NAME} PRIVATE -Wall -Wextra -Wpedantic)
endif()