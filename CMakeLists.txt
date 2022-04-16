set(CMAKE_C_COMPILER lcc)
cmake_minimum_required(VERSION 3.13)
project(helloworld C)
set(CMAKE_EXECUTABLE_SUFFIX ".gb")

add_executable(${PROJECT_NAME} main.c)
target_link_options(
    ${PROJECT_NAME}
    PRIVATE
    # Configure cartridge header
    # See https://github.com/gbdk-2020/gbdk-2020/blob/develop/gbdk-support/makebin/makebin.c#L109-L122 for a list of options
    -Wm-yj
    -Wm-yn${PROJECT_NAME}
)
