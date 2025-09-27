cmake_minimum_required(VERSION 3.10)
project(a60c C)

set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED ON)

# Add source files
set(FRONTEND_SOURCES
    defs.h
    frontend.h
    frontend.c
)
set(TRANSLATOR_SOURCES
    defs.h
    jff_header.h
    jff-algol.c
)

add_executable(a60c ${FRONTEND_SOURCES})
add_executable(a60t ${TRANSLATOR_SOURCES})

if(MSVC)
	target_compile_options(a60c PRIVATE -D_CRT_SECURE_NO_WARNINGS)
	target_compile_options(a60t PRIVATE -D_CRT_SECURE_NO_WARNINGS)
endif()


