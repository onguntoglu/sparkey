cmake_minimum_required(VERSION 3.25)
project(sparkey
  VERSION 0.1
  DESCRIPTION "Openlate project"
  LANGUAGES C)

set(CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}" ${CMAKE_MODULE_PATH})

set(CMAKE_EXPORT_COMPILE_COMMANDS TRUE)
set(CMAKE_POSITION_INDEPENDENT_CODE TRUE)
set(CMAKE_INTERPROCEDURAL_OPTIMIZATION TRUE)
set(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_USE_FOLDERS TRUE)

set(CMAKE_C_STANDARD 23)
set(CMAKE_C_STANDARD_REQUIRED TRUE)
set(CMAKE_C_EXTENSIONS TRUE)
set(CMAKE_C_KNOWN_FEATURES c_std_23)

set(CMAKE_BUILD_TYPE Release)
add_compile_options(
       $<$<CONFIG:RELEASE>:-Ofast>
       $<$<CONFIG:RELEASE>:-march=native>
       $<$<CONFIG:RELEASE>:-ffast-math>
       $<$<CONFIG:RELEASE>:-fverbose-asm>
       $<$<CONFIG:RELEASE>:-ftree-vectorize>
       $<$<CONFIG:RELEASE>:-pthread>

       $<$<CONFIG:DEBUG>:-Ofast>
       $<$<CONFIG:DEBUG>:-march=native>
       $<$<CONFIG:DEBUG>:-ffast-math>
       $<$<CONFIG:DEBUG>:-fverbose-asm>
       $<$<CONFIG:DEBUG>:-ftree-vectorize>
       $<$<CONFIG:DEBUG>:-ggdb3>
       $<$<CONFIG:DEBUG>:-pthread>
)

include_directories("${PROJECT_SOURCE_DIR}/include")

find_package(PkgConfig)
pkg_check_modules(snappy REQUIRED snappy)
pkg_check_modules(zstd REQUIRED libzstd)

add_subdirectory(src)
add_subdirectory(tests)
