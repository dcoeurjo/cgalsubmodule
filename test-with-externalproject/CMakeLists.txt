project(polyscope-CNC)
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(FetchContent)

FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG        release-1.8.0
  )

FetchContent_Declare(
  cgal
  GIT_REPOSITORY https://github.com/CGAL/cgal.git
  GIT_TAG        master
  )

FetchContent_MakeAvailable(googletest)

FetchContent_MakeAvailable(cgal)


add_executable(simpleTest simpleTest)

target_link_libraries(simpleTest CGAL::CGAL CGAL::Core)
