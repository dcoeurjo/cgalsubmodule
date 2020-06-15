project(polyscope-CNC)
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(FetchContent)



message("Downloading DGtal")
set(BUILD_EXAMPLES OFF CACHE INTERNAL "")
FetchContent_Declare(
  DGtal
  GIT_REPOSITORY https://github.com/DGtal-team/DGtal.git
  GIT_TAG        master
  GIT_SHALLOW    ON
  )
FetchContent_MakeAvailable(DGtal)

include("${DGtal_BINARY_DIR}/DGtalConfig.cmake")
include_directories("${DGTAL_INCLUDE_DIRS}")

add_executable(simpleTest2 simpleTest2)
target_link_libraries(simpleTest2 ${DGTAL_LIBRARIES} )


message("Downloading CGAL")
FetchContent_Declare(
  cgal
  GIT_REPOSITORY https://github.com/CGAL/cgal.git
  GIT_TAG        master
  GIT_SHALLOW    ON
  )
FetchContent_MakeAvailable(cgal)


add_executable(simpleTest simpleTest)
target_link_libraries(simpleTest  CGAL::CGAL CGAL::Core)

