cmake_minimum_required(VERSION 3.2)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(FetchContent)
FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG        main
)
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)

project(Vector)

## set(SRC_LIST
##     vector.cpp
## )

add_executable(${PROJECT_NAME} main.cpp ${SRC_LIST})
target_compile_options(${PROJECT_NAME} PUBLIC -Wall -Wpedantic -Wextra)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_SOURCE_DIR})

# unit tests
## enable_testing()
## add_executable(${PROJECT_NAME}-ut test.cpp ${SRC_LIST})
## target_link_libraries(${PROJECT_NAME}-ut gtest_main)

## include(GoogleTest)
## add_test(NAME tests COMMAND ${PROJECT_NAME}-ut) 
