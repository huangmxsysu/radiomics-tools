project(GrowCutSegmentation)

SET (EXECUTABLE_OUTPUT_PATH ${CMAKE_SOURCE_DIR}/bin)

INCLUDE_DIRECTORIES(../ITKUtils)

ADD_EXECUTABLE(NoduleSegmentation
    NoduleSegmentation.cxx
)

SET (BUILD_SHARED_LIBS OFF)
SET (CMAKE_VERBOSE_MAKEFILE OFF)

TARGET_LINK_LIBRARIES(NoduleSegmentation ${ITK_LIBRARIES} ITKUtils)


if(codecov_FOUND)
  add_coverage(NoduleSegmentation)
endif()
