set(EXE_TARGET_NAME control_module)

find_package(YARP REQUIRED)

set(${EXE_TARGET_NAME}_SRC
        main.cpp
)

set(${EXE_TARGET_NAME}_HDR
)

add_executable(${EXE_TARGET_NAME} ${${EXE_TARGET_NAME}_SRC} ${${EXE_TARGET_NAME}_HDR})

target_include_directories(${EXE_TARGET_NAME} PRIVATE "$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>")

target_link_libraries(${EXE_TARGET_NAME} ${YARP_LIBRARIES})

install(TARGETS ${EXE_TARGET_NAME} DESTINATION bin)
