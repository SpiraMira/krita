set( EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_BINARY_DIR} )
include_directories(   
    ${CMAKE_BINARY_DIR}/libs/image
)

include_directories(SYSTEM
    ${EIGEN3_INCLUDE_DIR}
)


macro_add_unittest_definitions()

########### next target ###############
set(kis_tiled_data_manager_test_SRCS kis_tiled_data_manager_test.cpp )
kde4_add_unit_test(KisTiledDataManagerTest TESTNAME krita-image-KisTiledDataManagerTest  ${kis_tiled_data_manager_test_SRCS})
target_link_libraries(KisTiledDataManagerTest   kritaimage Qt5::Test)

########### next target ###############
set(kis_low_memory_tests_SRCS kis_low_memory_tests.cpp )
kde4_add_unit_test(KisLowMemoryTests TESTNAME krita-image-KisLowMemoryTests  ${kis_low_memory_tests_SRCS})
target_link_libraries(KisLowMemoryTests   kritaimage Qt5::Test)
set_tests_properties(krita-image-KisLowMemoryTests PROPERTIES TIMEOUT 180)

########### next target ###############
#kisdoc
#set(kis_tile_compressors_test_SRCS kis_tile_compressors_test.cpp )
#kde4_add_unit_test(KisTileCompressorsTest TESTNAME krita-image-KisTileCompressorsTest  ${kis_tile_compressors_test_SRCS})
#target_link_libraries(KisTileCompressorsTest   kritaodf kritaimage Qt5::Test)

########### next target ###############
#kisdoc
#set(kis_compression_tests_SRCS kis_compression_tests.cpp )
#kde4_add_unit_test(KisCompressionTests TESTNAME krita-image-KisCompressionTests  ${kis_compression_tests_SRCS})
#target_link_libraries(KisCompressionTests   kritaimage Qt5::Test)

########### next target ###############
set(kis_lockless_stack_test_SRCS kis_lockless_stack_test.cpp )
kde4_add_unit_test(KisLocklessStackTest TESTNAME krita-image-KisLocklessStackTest  ${kis_lockless_stack_test_SRCS})
target_link_libraries(KisLocklessStackTest   kritaimage Qt5::Test)

########### next target ###############
set(kis_memory_pool_test_SRCS kis_memory_pool_test.cpp )
kde4_add_unit_test(KisMemoryPoolTest TESTNAME krita-image-KisMemoryPoolTest  ${kis_memory_pool_test_SRCS})
target_link_libraries(KisMemoryPoolTest  kritaglobal  Qt5::Test)

########### next target ###############
set(kis_chunk_allocator_test_SRCS kis_chunk_allocator_test.cpp ../swap/kis_chunk_allocator.cpp)
kde4_add_unit_test(KisChunkAllocatorTest TESTNAME krita-image-KisChunkAllocatorTest  ${kis_chunk_allocator_test_SRCS})
target_link_libraries(KisChunkAllocatorTest kritaglobal  Qt5::Test)

########### next target ###############
set(kis_memory_window_test_SRCS kis_memory_window_test.cpp ../swap/kis_memory_window.cpp)
kde4_add_unit_test(KisMemoryWindowTest TESTNAME krita-image-KisMemoryWindowTest  ${kis_memory_window_test_SRCS})
target_link_libraries(KisMemoryWindowTest kritaglobal  Qt5::Test)

########### next target ###############
set(kis_swapped_data_store_test_SRCS kis_swapped_data_store_test.cpp ../kis_tile_data.cc)
kde4_add_unit_test(KisSwappedDataStoreTest TESTNAME krita-image-KisSwappedDataStoreTest  ${kis_swapped_data_store_test_SRCS})
target_link_libraries(KisSwappedDataStoreTest   kritaimage Qt5::Test ${Boost_SYSTEM_LIBRARY})

########### next target ###############
set(kis_tile_data_store_test_SRCS kis_tile_data_store_test.cpp ../kis_tile_data.cc)
kde4_add_broken_unit_test(KisTileDataStoreTest TESTNAME krita-image-KisTileDataStoreTest  ${kis_tile_data_store_test_SRCS})
target_link_libraries(KisTileDataStoreTest   kritaimage Qt5::Test ${Boost_SYSTEM_LIBRARY})

########### next target ###############
set(kis_store_limits_test_SRCS kis_store_limits_test.cpp ../kis_tile_data.cc )
kde4_add_broken_unit_test(KisStoreLimitsTest TESTNAME krita-image-KisStoreLimitsTest  ${kis_store_limits_test_SRCS})
target_link_libraries(KisStoreLimitsTest   kritaimage Qt5::Test ${Boost_SYSTEM_LIBRARY})

########### next target ###############
set(kis_tile_data_pooler_test_SRCS kis_tile_data_pooler_test.cpp ../kis_tile_data.cc ../kis_tile_data_pooler.cc )
kde4_add_unit_test(KisTileDataPoolerTest TESTNAME krita-image-KisTileDataPoolerTest  ${kis_tile_data_pooler_test_SRCS})
target_link_libraries(KisTileDataPoolerTest   kritaimage Qt5::Test ${Boost_SYSTEM_LIBRARY})

