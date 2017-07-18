set(EXE_TARGET_NAME module1)

find_package(OpenCV REQUIRED)
find_package(YARP   REQUIRED)

LIST(APPEND CMAKE_MODULE_PATH ${YARP_MODULE_PATH})

set(${EXE_TARGET_NAME}_SRC
        src/main.cpp
)

set(${EXE_TARGET_NAME}_HDR
)

add_executable(${EXE_TARGET_NAME} ${${EXE_TARGET_NAME}_SRC} ${${EXE_TARGET_NAME}_HDR})

target_include_directories(${EXE_TARGET_NAME} PRIVATE "$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>"
                                                      ${YARP_INCLUDE_DIRS})

target_link_libraries(${EXE_TARGET_NAME} ${OpenCV_LIBS}
                                         ${YARP_LIBRARIES})

install(TARGETS ${EXE_TARGET_NAME} DESTINATION bin)
