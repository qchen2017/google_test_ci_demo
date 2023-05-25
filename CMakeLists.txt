# Required by FetchContent_MakeAvailable
cmake_minimum_required(VERSION 3.14)
project(Foo)

# for gtest
# find_package(GTest)
# include_directories(${GTEST_INCLUDE_DIRS})
# MESSAGE(${GTEST_INCLUDE_DIRS})
# MESSAGE(${GTEST_BOTH_LIBRARIES})
# MESSAGE(${GTEST_LIBRARIES})
# MESSAGE(${GTEST_MAIN_LIBRARIES})

include(FetchContent)
FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG        release-1.11.0
)
FetchContent_MakeAvailable(googletest)

# set(CMAKE_CXX_STANDARD 11)
# set(TEST_NAME ${PROJECT_NAME}_tests)
# add_executable(${TEST_NAME} foo_test.cc)
# target_link_libraries(${TEST_NAME} gtest_main)

# target_link_libraries(${TEST_NAME} ${GTEST_BOTH_LIBRARIES} pthread)
# target_link_libraries(${TEST_NAME} GTest::GTest GTest::Main pthread)
# target_link_libraries(${TEST_NAME} gtest_main pthread)

enable_testing()
include(GoogleTest)
gtest_discover_tests(${TEST_NAME})
