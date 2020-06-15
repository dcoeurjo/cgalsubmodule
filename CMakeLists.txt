project(polyscope-CNC)
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(deps)


add_executable(simpleTest simpleTest)
target_link_libraries(simpleTest CGAL::Core)
