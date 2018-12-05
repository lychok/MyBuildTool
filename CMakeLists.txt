set(APP_NAME "Lych Framework")
set(APP_PROJECT "πø∂√ålå")
set(APP_DESC "C++ framework")
set(APP_AUTH "lychok@gmail.com")
set(CMAKE_VERSION_NEED 3.12)
cmake_minimum_required(VERSION ${CMAKE_VERSION_NEED})
if (CMAKE_VERSION VERSION_LESS ${CMAKE_VERSION_NEED})
    message(FATAL_ERROR "CMake version ${CMAKE_VERSION_NEED}+ requires")
endif()
if (NOT CMAKE_VERSION VERSION_LESS ${CMAKE_VERSION_NEED})
    message(STATUS "Art Framework requires at CMake version less ${CMAKE_VERSION_NEED}+")
endif()
project(${APP_PROJECT})

if(NOT CMAKE_BUILD_TYPE)
set(CMAKE_BUILD_TYPE "Release") # Debug, Release, RelWithDebInfo and MinSizeRel.
endif()

include(cmake/ArtMain.cmake)
include(cmake/ArtVoids.cmake)
include(cmake/ArtQt.cmake)

enable_testing()
# MΩNΩlych building

add_subdirectory(libs/Lych/Core)
add_subdirectory(libs/Lych/LineNoise)

#add_subdirectory(src/Lych)
add_subdirectory(src/ided)
add_subdirectory(src/Widget)

add_custom_target(
    del DEPENDS COMMAND ${CMAKE_SOURCE_DIR}/tools/del
)
