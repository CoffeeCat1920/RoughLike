cmake_minimum_required(VERSION 4.0)
set(PROJECT_NAME "roughlike")

project(${PROJECT_NAME} LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_subdirectory(include)

add_executable(${PROJECT_NAME})

find_package(raylib REQUIRED)

target_link_libraries(${PROJECT_NAME}
  PRIVATE Includes
  PUBLIC raylib 
)

target_sources(${PROJECT_NAME}
  PRIVATE 
    main.cpp
)

