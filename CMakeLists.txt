cmake_minimum_required(VERSION 2.8.0)

project(gatttool)

include_directories(.)
include_directories(src)
include_directories(attrib)
include_directories(btio)
include_directories(src/shared)
include_directories(lib)
include_directories(client)
include_directories(monitor)
include_directories(profiles)
include_directories(/usr/include/glib-2.0) 
include_directories(/usr/lib/x86_64-linux-gnu/glib-2.0/include)

file (GLOB_RECURSE HEADER src/*.h attrib/*.h btio/*.h src/shared/*.h lib/*.h client/*.h monitor/*.h profiles/*.h)
file (GLOB_RECURSE SOURCE src/*.c attrib/*.c btio/*.c src/shared/*.c lib/*.c client/*.c monitor/*.c profiles/*.c)

add_executable(gatttool ${HEADER} ${SOURCE})
target_link_libraries(gatttool bluetooth readline glib-2.0)
