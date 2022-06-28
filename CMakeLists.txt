CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
PROJECT(PA1 CXX)
SET(CMAKE_BUILD_TYPE "Release")
SET(CMAKE_CXX_FLAGS_DEBUG "$ENV{CXXFLAGS} -O0 -Wall -g2 -ggdb -fopenmp")
SET(CMAKE_CXX_FLAGS_RELEASE "$ENV{CXXFLAGS} -O3 -Wall -fopenmp")
IF(NOT CMAKE_BUILD_TYPE)
    SET(CMAKE_BUILD_TYPE Release)
ENDIF()

SET(PA1_SOURCES
        src/main.cpp
        )

SET(PA1_INCLUDES
        include/vec3.hpp
        include/color.hpp
        include/ray.hpp
        include/hittable.hpp
        include/sphere.hpp
        include/hittable_list.hpp
        include/utils.hpp
        include/camera.hpp
        include/material.hpp
        include/moving_sphere.hpp
        include/aabb.hpp
        include/bvh.hpp
        include/texture.hpp
        include/perlin.hpp
        include/stb_image.hpp
        include/aarect.hpp
        include/constant_medium.hpp
        )

SET(CMAKE_CXX_COMPILER "/opt/homebrew/bin/g++-11")
SET(CMAKE_CXX_STANDARD 11)
SET(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)

ADD_EXECUTABLE(${PROJECT_NAME} ${PA1_SOURCES} ${PA1_INCLUDES})
TARGET_INCLUDE_DIRECTORIES(${PROJECT_NAME} PRIVATE include)
