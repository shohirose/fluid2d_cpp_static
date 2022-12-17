cmake_minimum_required(VERSION 3.21)
project(fluid2d_cpp_static)

add_executable(fluid2d
    src/main.cpp
    )
target_include_directories(fluid2d
    PRIVATE
        src/
    )
target_compile_options(fluid2d
    PRIVATE
        $<$<CXX_COMPILER_ID:MSVC>:/W4>
        $<$<CXX_COMPILER_ID:GNU>:-Wall -Werror -Wpedantic>
        $<$<CXX_COMPILER_ID:Clang>:-Wall -Werror -Wpedantic>
        $<$<CXX_COMPILER_ID:Intel>:$<IF:$<PLATFORM_ID:Windows>,/W3,-w3>>
        $<$<CXX_COMPILER_ID:IntelLLVM>:$<IF:$<PLATFORM_ID:Windows>,/W3,-w3>>
    )