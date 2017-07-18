cmake_minimum_required(VERSION 3.1)

project(easy-peasy-modules
        LANGUAGES CXX
        VERSION 1.0.0.0)

find_package(ICUBcontrib REQUIRED)
list(APPEND CMAKE_MODULE_PATH ${ICUBCONTRIB_MODULE_PATH})
include(ICUBcontribHelpers)
include(ICUBcontribOptions)
icubcontrib_set_default_prefix()
icubcontrib_add_uninstall_target()

add_subdirectory(src)
