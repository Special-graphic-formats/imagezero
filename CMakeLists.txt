cmake_minimum_required(VERSION 2.8)

project(imagezero)

set(CMAKE_BUILD_TYPE "Release")

set(MAJOR_VERSION 0)
set(RELEASE_VERSION 2.5)
set(IZ_VERSION ${MAJOR_VERSION}.${RELEASE_VERSION})

set(libiz_SRCS
    src/libiz.cpp
    src/table.cpp
)

set(iz_SRCS
    src/file.cpp
    src/main.cpp
    src/portableimage.cpp
)

add_definitions(-DHAVE_MMAP)

set(CMAKE_EXE_LINKER_FLAGS "-Wl,-O1,-s,--no-export-dynamic")
set(CMAKE_CXX_FLAGS_RELEASE "-O2 -mmmx -mtune=atom -Winline -W -Wall -fomit-frame-pointer -fno-rtti -fno-exceptions")

add_library(${PROJECT_NAME}
    SHARED
    ${libiz_SRCS}
  )
set_target_properties(${PROJECT_NAME} PROPERTIES VERSION ${IZ_VERSION} SOVERSION ${MAJOR_VERSION})

add_executable(iz
    ${iz_SRCS}
  )

target_link_libraries(iz
    ${PROJECT_NAME}
  )
