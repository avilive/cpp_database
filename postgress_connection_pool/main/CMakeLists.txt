project(pstgress_connection_pool)



add_executable(${PROJECT_NAME} main.cpp)

#message( SEND_MESSAGE " "${CMAKE_MODULE_PATH} )
#target_link_libraries(${PROJECT_NAME} gtest gmock gtest_main)



add_test(SimpleTest SimpleTest)

#find_package(GTest REQUIRED)



#if (GTest_FOUND)
#   include_directories(${GTEST_INCLUDE_DIRS}) 
#    add_executable(main_cli main.cpp) 
#  target_link_libraries(${PROJECT_NAME} ${GTEST_LIBRARIES})
#   message( SEND_MESSAGE ${GTEST_INCLUDE_DIRS} )
#else()    
#   message( SEND_ERROR "GTEST NOT FOUND" )
#endif()
#target_link_libraries(${PROJECT_NAME} pgconnection pgbackend)  #libpq
#message( SEND_MESSAGE sub::pgbackend)
target_link_libraries(${PROJECT_NAME}
    sub::pgbackend
    sub::pgconnection
)