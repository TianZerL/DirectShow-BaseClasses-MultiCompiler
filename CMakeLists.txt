cmake_minimum_required(VERSION 3.15)

if(NOT CMAKE_BUILD_TYPE)
    message(STATUS "Set default build type to Release")
    set(CMAKE_BUILD_TYPE Release CACHE STRING "Build Type" FORCE)
endif()

project(DirectShowBaseclasses LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(BASECLASSES_DIR ${CMAKE_CURRENT_SOURCE_DIR}/baseclasses)

add_library(strmbase STATIC
    ${BASECLASSES_DIR}/amextra.cpp
    ${BASECLASSES_DIR}/amfilter.cpp
    ${BASECLASSES_DIR}/amvideo.cpp
    ${BASECLASSES_DIR}/arithutil.cpp
    ${BASECLASSES_DIR}/combase.cpp
    ${BASECLASSES_DIR}/cprop.cpp
    ${BASECLASSES_DIR}/ctlutil.cpp
    ${BASECLASSES_DIR}/ddmm.cpp
    ${BASECLASSES_DIR}/dllentry.cpp
    ${BASECLASSES_DIR}/dllsetup.cpp
    ${BASECLASSES_DIR}/mtype.cpp
    ${BASECLASSES_DIR}/outputq.cpp
    ${BASECLASSES_DIR}/perflog.cpp
    ${BASECLASSES_DIR}/pstream.cpp
    ${BASECLASSES_DIR}/pullpin.cpp
    ${BASECLASSES_DIR}/refclock.cpp
    ${BASECLASSES_DIR}/renbase.cpp
    ${BASECLASSES_DIR}/schedule.cpp
    ${BASECLASSES_DIR}/seekpt.cpp
    ${BASECLASSES_DIR}/source.cpp
    ${BASECLASSES_DIR}/strmctl.cpp
    ${BASECLASSES_DIR}/sysclock.cpp
    ${BASECLASSES_DIR}/transfrm.cpp
    ${BASECLASSES_DIR}/transip.cpp
    ${BASECLASSES_DIR}/videoctl.cpp
    ${BASECLASSES_DIR}/vtrans.cpp
    ${BASECLASSES_DIR}/winctrl.cpp
    ${BASECLASSES_DIR}/winutil.cpp
    ${BASECLASSES_DIR}/wxdebug.cpp
    ${BASECLASSES_DIR}/wxlist.cpp
    ${BASECLASSES_DIR}/wxutil.cpp
)

target_include_directories(strmbase PUBLIC $<BUILD_INTERFACE:${BASECLASSES_DIR}>)
target_link_libraries(strmbase PRIVATE strmiids winmm)
