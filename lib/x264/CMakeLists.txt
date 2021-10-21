cmake_minimum_required(VERSION 3.14)
project(x264)

find_package(PkgConfig REQUIRED)
pkg_check_modules(X264	REQUIRED IMPORTED_TARGET x264)

add_library(x264 INTERFACE IMPORTED GLOBAL)
target_include_directories(x264 INTERFACE
    ${X264_INCLUDE_DIRS}
)
target_link_options(x264 INTERFACE
    ${X264_LDFLAGS}
)
