# CMakeList.txt : CMake project for RocketSim, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

# Enable Hot Reload for MSVC compilers if supported.
if (POLICY CMP0141)
  cmake_policy(SET CMP0141 NEW)
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

project ("RocketSim")

# Add source to this project's executable.
add_executable (RocketSim "RocketSim.cpp" "RocketSim.h")



find_package(Bullet CONFIG REQUIRED)

if (BULLET_FOUND)
  include_directories(${BULLET_INCLUDE_DIRS})
  target_link_directories(RocketSim PRIVATE ${BULLET_LIBRARY_DIRS})
  target_link_libraries(RocketSim PRIVATE BulletDynamics BulletCollision Bullet3Common	LinearMath)
endif (BULLET_FOUND)

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET RocketSim PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.
