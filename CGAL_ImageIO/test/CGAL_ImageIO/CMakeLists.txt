# Created by the script cgal_create_cmake_script
# This is the CMake script for compiling a CGAL application.

cmake_minimum_required(VERSION 3.1...3.23)
project(CGAL_ImageIO_Tests)

find_package(CGAL REQUIRED COMPONENTS ImageIO)

if(WITH_CGAL_ImageIO)
  create_single_source_cgal_program("test_trilinear_interpolation.cpp")
else()
  message(
    STATUS
      "NOTICE: Some tests require the CGAL_ImageIO library, and will not be compiled."
  )
endif()
