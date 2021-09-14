project(maintest)

ADD_EXECUTABLE(string_compare string_compare.cpp)
#ADD_EXECUTABLE(maintest maintest.cpp)


#add_test(NAME string_compare
#         COMMAND string_compare)



add_executable(maintest maintest.cpp)
enable_testing() # Must be in main file


#message( SEND_MESSAGE " "${CMAKE_MODULE_PATH} )
include(AddGoogleTest.cmake) # Could be in /tests/CMakeLists.txt
#target_link_libraries(${PROJECT_NAME} gtest gmock gtest_main)

add_gtest(maintest maintest.cpp)
add_gtest(string_compare string_compare.cpp)
#add_test(SimpleTest SimpleTest)
#
#find_package(GTest REQUIRED)
#
#if (GTest_FOUND)
#    include_directories(${GTEST_INCLUDE_DIRS}) 
#    add_executable(main_cli main.cpp) 
#   target_link_libraries(${PROJECT_NAME} ${GTEST_LIBRARIES})
#   message( SEND_MESSAGE ${GTEST_INCLUDE_DIRS} )
#else()    
#   message( SEND_ERROR "GTEST NOT FOUND" )
#endif()

#target_link_libraries(${PROJECT_NAME} pgconnection pgbackend) #libpq