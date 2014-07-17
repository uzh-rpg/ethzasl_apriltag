add_executable(april_node main.cpp april_interface.cpp Params.cpp)
target_link_libraries(april_node ${catkin_LIBRARIES} ${OpenCV_LIBS} pthread)
add_dependencies(april_node ${PROJECT_NAME}_gencfg)

