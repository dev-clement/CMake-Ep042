cmake_minimum_required(VERSION 3.28)

project(CppProjectTemplate
        VERSION 0.0.1
        LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD          17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS       OFF)

option(ENABLE_TESTING "Enable the unit testing build" ON)

set(LIBRARY_NAME Library)
set(EXECUTABLE_NAME Executable)

set(CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake/")

include(AddJsonParser)
include(AddFmt)
include(AddSpdLog)
include(AddCxxOpts)
include(Docs)

add_subdirectory(configure/)
add_subdirectory(my_lib/)
add_subdirectory(app/)
if (ENABLE_TESTING)
    enable_testing()
    add_subdirectory(tests/)
endif()
