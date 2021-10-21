cmake_minimum_required(VERSION 3.14)
project(x265)

find_package(PkgConfig REQUIRED)
pkg_check_modules(X265	REQUIRED IMPORTED_TARGET x265)

add_library(x265 INTERFACE IMPORTED GLOBAL)
target_include_directories(x265 INTERFACE
    ${X265_INCLUDE_DIRS}
)
target_link_options(x265 INTERFACE
    ${X265_LDFLAGS}
)
