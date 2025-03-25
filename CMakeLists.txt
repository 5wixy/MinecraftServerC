cmake_minimum_required(VERSION 3.30)
project(MinecraftServerC)

set(CMAKE_C_STANDARD 23)


add_executable(server
        main.c
        socket_utils.c
        packet_utils.c
        packet_utils.h
        handshake.c
        handshake.h
        socket_utils.h
        login.c
        login.h
        Externals/cJSON.c
        Externals/cJSON.h
        Externals/libnbt/libnbt/miniz.c
        Externals/libnbt/libnbt/miniz.H
        nbt_impl.c
        extract_uuid.c
        extract_uuid.h
        play.c
        play.h
)

include_directories(F:/MinecraftserverC/Externals/libnbt/libnbt)

target_link_libraries(server ws2_32)

find_package(CURL REQUIRED)
target_link_libraries(server CURL::libcurl)
