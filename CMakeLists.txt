cmake_minimum_required(VERSION 4.1)
project(sfml_MSVC)

set(CMAKE_CXX_STANDARD 20)

add_executable(sfml_MSVC main.cpp)


target_include_directories(sfml_MSVC PRIVATE ${PROJECT_SOURCE_DIR}/include)

add_definitions(-DSFML_STATIC)  # Required for static linking
target_link_libraries(sfml_MSVC
        "${PROJECT_SOURCE_DIR}/lib/sfml-graphics-s.lib"
        "${PROJECT_SOURCE_DIR}/lib/sfml-window-s.lib"
        "${PROJECT_SOURCE_DIR}/lib/sfml-system-s.lib"
        opengl32
        winmm
        gdi32
        "${PROJECT_SOURCE_DIR}/lib/freetype.lib"
)