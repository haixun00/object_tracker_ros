cmake_minimum_required(VERSION 2.8.12)

include($ENV{ROS_ROOT}/core/rosbuild/rosbuild.cmake)

rosbuild_init()

find_package(OpenCV 3.1 REQUIRED)

#compile tracker full version

#add_subdirectory(dlib)
#rosbuild_add_executable(object_tracker src/tracker.cpp)
#rosbuild_add_compile_flags(object_tracker -std=c++11)
#TARGET_LINK_LIBRARIES(object_tracker ${OpenCV_LIBS} dlib::dlib)


#compile testing
rosbuild_add_executable(tracker src/tracker.cpp src/Hungarian.h src/Hungarian.cpp)
rosbuild_add_compile_flags(tracker -std=c++11)
TARGET_LINK_LIBRARIES(tracker ${OpenCV_LIBS})
#TARGET_LINK_LIBRARIES(tracker ${OpenCV_LIBS} dlib::dlib)



