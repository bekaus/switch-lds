PROJECT(switch-lds)

#
# dependencies
#
include_directories(${PROJECT_SOURCE_DIR}/include/)


#
# build options
#
# unit tests
set(WITH_TESTS "False" CACHE BOOL "Build tests.")


#
# libswitchlds
#

file(GLOB LIB_SOURCES src/*.cpp)
add_library(switchlds SHARED ${LIB_SOURCES})

# Tests
if(WITH_TESTS)
  enable_testing()
  add_subdirectory(tests/)
endif()
