cmake_minimum_required(VERSION 3.22.1)

project(pairipcore)

add_library(pairipcore SHARED
        src/library.cpp
        src/armhook.c
        src/inlinehook.c
        src/mem.c
        src/memscan.c
        src/proc.c
)

target_link_options(pairipcore PRIVATE
    -Wl,-z,max-page-size=16384
    -Wl,-z,common-page-size=16384
)

target_link_libraries(pairipcore
        android
        log
)
