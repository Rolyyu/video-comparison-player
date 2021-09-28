cmake_minimum_required(VERSION 3.14)
project(video-comparison-player C CXX)
set(CMAKE_CXX_STANDARD 11)

add_subdirectory(src)
add_subdirectory(lib/ffmpeg)
add_subdirectory(lib/sdl)

add_executable(vcplayer ${SOURCES})
target_link_libraries(vcplayer ffmpeg sdl)
