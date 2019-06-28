cmake_minimum_required(VERSION 2.8.3)
project(libqudt)

# --- Libraries ----------------------------------------------------------------

include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}/src
)

set(QUDT_SOURCES
  src/libqudt.cpp
)

set(QUDT_HEADERS
  src/libqudt.cpp
)

add_library(qudt ${QUDT_SOURCES} ${QUDT_HEADERS})

install(TARGETS qudt
  DESTINATION lib
)
