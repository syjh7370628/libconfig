if(CMAKE_HOST_WIN32)
    set(libname "libconfig")
else()
    set(libname "config")
endif()

include_directories(${CMAKE_SOURCE_DIR}/lib)

add_executable(libconfig_tests
    tests.c
)

target_link_libraries(libconfig_tests
    ${libname}
    libtinytest
)

add_test(
    NAME libconfig_tests
    COMMAND libconfig_tests
    WORKING_DIRECTORY ${CMAKE_SOURCE_DIR}/tests
)
