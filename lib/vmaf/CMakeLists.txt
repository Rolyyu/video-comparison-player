cmake_minimum_required(VERSION 3.14)
project(vmaf)

find_package(PkgConfig REQUIRED)
pkg_check_modules(VMAF	REQUIRED IMPORTED_TARGET libvmaf)

add_library(vmaf INTERFACE IMPORTED GLOBAL)
target_include_directories(vmaf INTERFACE
    ${VMAF_INCLUDE_DIRS}
)
target_link_options(vmaf INTERFACE
    ${VMAF_LDFLAGS}
)
