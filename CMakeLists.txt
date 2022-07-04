# Copyright 2018 Mike Dev
# Distributed under the Boost Software License, Version 1.0.
# (http://www.boost.org/LICENSE_1_0.txt)

if(NOT DEFINED IDF_TARGET)

cmake_minimum_required(VERSION 3.5...3.20)

project(boost_io VERSION "${BOOST_SUPERPROJECT_VERSION}" LANGUAGES CXX)

add_library(boost_io INTERFACE)
add_library(Boost::io ALIAS boost_io)

target_include_directories(boost_io INTERFACE include)

target_link_libraries(boost_io
  INTERFACE
    Boost::config
)

else()

idf_component_register(
    INCLUDE_DIRS
        include
    REQUIRES
        boost_config
)

endif()
