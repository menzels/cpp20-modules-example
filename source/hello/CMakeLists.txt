cmake_minimum_required(VERSION 3.25)
project(hello LANGUAGES CXX)

include(GenerateExportHeader)

add_library(hello)

generate_export_header(hello)

target_sources(
  hello
  PUBLIC
  FILE_SET HEADERS
  BASE_DIRS "${CMAKE_CURRENT_BINARY_DIR}"
  FILES "${CMAKE_CURRENT_BINARY_DIR}/hello_export.h"
  FILE_SET cxx_modules
  TYPE CXX_MODULES
  FILES hello.cpp
)
