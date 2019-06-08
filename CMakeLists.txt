project("uno-base")
cmake_minimum_required(VERSION 2.8)

include(cmake/modules/library.cmake)
include_directories(${PROJECT_SOURCE_DIR}/include)
link_directories(${LIBRARY_OUTPUT_PATH})

if (APPLE)
    set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wno-switch-enum -Wno-logical-op-parentheses -Wno-parentheses-equality -Wno-extra-tokens -Wno-deprecated-declarations")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wno-switch-enum -Wno-logical-op-parentheses -Wno-parentheses-equality")
endif()


add_subdirectory(src/harfbuzz)
