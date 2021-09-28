cmake_minimum_required(VERSION 3.14)
project(sdl)

find_package(PkgConfig REQUIRED)
pkg_check_modules(SDL  REQUIRED IMPORTED_TARGET sdl)

add_library(sdl INTERFACE IMPORTED GLOBAL)
target_include_directories(sdl INTERFACE
    ${SDL_INCLUDE_DIRS}
)
target_link_options(sdl INTERFACE
    ${SDL_LDFLAGS}
)
