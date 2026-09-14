cmake_minimum_required(VERSION 3.16)

project(calculator LANGUAGES C)

# TODO: create an executable target named calculator
add_executable(calculator
    src/calculator.c
    src/main.c
)
# Hint: sources are in src/main.c and src/calculator.c

# TODO: add the include directory for the calculator target
target_include_directories(calculator
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include
)
