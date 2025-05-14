cmake_minimum_required(VERSION 3.10)
project(BowlingGame)

set(CMAKE_CXX_STANDARD 17)

# Find GTest
find_package(GTest REQUIRED)
include_directories(${GTEST_INCLUDE_DIRS})

# Main executable
include_directories(include)
add_executable(BowlingGame src/main.cpp)

# Test executable
add_executable(BowlingTests tests/test.cpp)
target_link_libraries(BowlingTests ${GTEST_LIBRARIES} pthread)

# Enable testing
enable_testing()
add_test(NAME BowlingTests COMMAND BowlingTests)