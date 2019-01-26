cmake_minimum_required(VERSION 3.6)
project(ED_Lib)

set(CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR /usr/local/opt/opencv@3/share/OpenCV)
find_package(OpenCV 3)
include_directories(${OpenCV_INCLUDE_DIRS})

add_library(EDLib STATIC
        ED.cpp
        ED.h
        EDCircles.cpp
        EDCircles.h
        EDColor.cpp
        EDColor.h
        EDLib.h
        EDLines.cpp
        EDLines.h
        EDPF.cpp
        EDPF.h
        NFA.cpp
        NFA.h)

add_executable(test test.cpp)
target_link_libraries(test ${OpenCV_LIBS} EDLib)