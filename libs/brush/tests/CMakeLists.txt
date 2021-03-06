########### next target ###############

set( EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_BINARY_DIR} )
include_directories(    
    ${CMAKE_SOURCE_DIR}/libs/image/metadata 
    ${CMAKE_SOURCE_DIR}/sdk/tests 
)
include_directories(SYSTEM
    ${EIGEN3_INCLUDE_DIR}
)

if(HAVE_VC)
  include_directories(SYSTEM
      ${Vc_INCLUDE_DIR}
  )
endif()



macro_add_unittest_definitions()

########### next target ###############

set(kis_auto_brush_test_SRCS kis_auto_brush_test.cpp )
kde4_add_unit_test(KisAutoBrushTest TESTNAME krita-libbrush-KisAutoBrushTest ${kis_auto_brush_test_SRCS})
target_link_libraries(KisAutoBrushTest   kritaimage kritalibbrush  Qt5::Test)

########### next target ###############

set(kis_gbr_brush_test_SRCS kis_gbr_brush_test.cpp )
kde4_add_unit_test(KisGbrBrushTest TESTNAME krita-libbrush-KisGbrBrushTest ${kis_gbr_brush_test_SRCS})
target_link_libraries(KisGbrBrushTest   kritaimage kritalibbrush  Qt5::Test)

########### next target ###############

set(kis_boundary_test_SRCS kis_boundary_test.cpp )
kde4_add_unit_test(KisBoundaryTest TESTNAME krita-libbrush-KisBoundaryTest ${kis_boundary_test_SRCS})
target_link_libraries(KisBoundaryTest   kritaimage kritalibbrush  Qt5::Test)

########### next target ###############

set(kis_imagepipe_brush_test_SRCS kis_imagepipe_brush_test.cpp )
kde4_add_unit_test(KisImagePipeBrushTest TESTNAME krita-libbrush-KisImagePipeBrushTest ${kis_imagepipe_brush_test_SRCS})
target_link_libraries(KisImagePipeBrushTest   kritaimage kritalibbrush  Qt5::Test)
