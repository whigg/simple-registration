#/*============================================================================
#
#  research-computing-with-cpp-demo: CMake based demo code.
#
#  Copyright (c) University College London (UCL). All rights reserved.
#
#  This software is distributed WITHOUT ANY WARRANTY; without even
#  the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR
#  PURPOSE.
#
#  See LICENSE.txt in the top level directory for details.
#
#============================================================================*/

add_library(PointMatching Exceptions.cc Util.cc PointMatching.cc)
target_link_libraries(PointMatching ${Boost_LIBRARIES})

add_executable(PointMatchingCmd PointMatchingCmd.cc)
target_link_libraries(PointMatchingCmd PointMatching ${Boost_LIBRARIES})

add_library(SurfaceBasedRegistration SurfaceBasedRegistration.cc)
target_link_libraries(SurfaceBasedRegistration PointMatching ${Boost_LIBRARIES})

add_executable(SurfaceBasedRegistrationCmd SurfaceBasedRegistrationCmd.cc)
target_link_libraries(SurfaceBasedRegistrationCmd SurfaceBasedRegistration ${Boost_LIBRARIES})
