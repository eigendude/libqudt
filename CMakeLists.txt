cmake_minimum_required(VERSION 2.8.3)
project(libqudt)

# --- Standards ----------------------------------------------------------------

set(CMAKE_C_STANDARD 11)

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

# --- Resources ----------------------------------------------------------------

# TODO: Glob files
set(QUDT_RESOURCES
  res/dimension
  res/dtype
  res/ops.ttl
  res/quantity
  res/qudt
  res/qudt-quantity
  res/unit
)

install(
  FILES
    ${QUDT_RESOURCES}
  DESTINATION
    share/qudt
)
