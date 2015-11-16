project(OculusSDK)

cmake_minimum_required(VERSION 2.8)

include(cmake/defaults.cmake)

set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -DOVR_BUILD_DEBUG")

# The primary SDK artifact, a static library for Oculus access 
add_subdirectory(LibOVR)
set_target_properties(OculusVR PROPERTIES FOLDER "Oculus")

install(DIRECTORY ${PROJECT_SOURCE_DIR}/3rdParty/glext/ DESTINATION "${CMAKE_INSTALL_PREFIX}/include")
install(FILES ${PROJECT_SOURCE_DIR}/LICENSE.TXT DESTINATION "${CMAKE_INSTALL_PREFIX}/")