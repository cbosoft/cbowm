cmake_minimum_required(VERSION 3.13)
set(EXE cbowm)
project(${EXE})
set(CMAKE_CXX_STANDARD 14)

file(GLOB SOURCE_FILES "*.c*")

find_package(X11 REQUIRED)
find_package(Freetype REQUIRED)

message("X11: ${X11_INCLUDE_DIR} || ${X11_LIBRARIES}")
message("Freetype: ${FREETYPE_INCLUDE_DIRS} || ${FREETYPE_LIBRARIES}")

add_executable(${EXE} ${SOURCE_FILES} ${X11_LIBRARIES} ${FREETYPE_LIBRARIES})

target_include_directories(${EXE} PRIVATE ${X11_INCLUDE_DIR})
target_include_directories(${EXE} PRIVATE ${FREETYPE_INCLUDE_DIRS})