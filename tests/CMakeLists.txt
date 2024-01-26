add_executable(sparkey-bench "bench.c")
target_link_libraries(sparkey-bench PRIVATE libsparkey)
target_include_directories(sparkey-bench PRIVATE "${PROJECT_SOURCE_DIR}/src")

# add_executable(test-hash "testhash.c")
# target_link_libraries(test-hash PRIVATE libsparkey)
# target_include_directories(test-hash PRIVATE "${PROJECT_SOURCE_DIR}/src")

# add_executable(test-system "testsystem.c")
# target_link_libraries(test-system PRIVATE libsparkey)
# target_include_directories(test-system PRIVATE "${PROJECT_SOURCE_DIR}/src")

# add_executable(test-util "testutil.c")
# target_link_libraries(test-util PRIVATE libsparkey)
# target_include_directories(test-util PRIVATE "${PROJECT_SOURCE_DIR}/src")

# add_executable(test-vlq "testvlq.c")
# target_link_libraries(test-vlq PRIVATE libsparkey)
# target_include_directories(test-vlq PRIVATE "${PROJECT_SOURCE_DIR}/src")
