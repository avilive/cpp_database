cmake_minimum_required(VERSION 3.10)

project(pstgress_connection_pool)

SET(CMAKE_CXX_FLAGS "-std=c++17 -pthread -O3 -pedantic -Wall -Werror")

enable_testing()

find_package(PostgreSQL REQUIRED)
#if (NOT PostgreSQL_FOUND)
 #   message( SEND_ERROR "POSTGRES NOT FOUND" )
#else()    
    #message( SEND_MESSAGE ${PostgreSQL_LIBRARIES})
    #message( SEND_MESSAGE ${PostgreSQL_INCLUDE_DIRS})
    #message( SEND_MESSAGE ${PostgreSQL_LIBRARY_DIRS})
 #  message( SEND_MESSAGE ${PostgreSQL_VERSION_STRING})
#endif()

add_subdirectory(pgconnection)
add_subdirectory(pgbackend)
add_subdirectory(main)
#add_subdirectory(test)
#add_subdirectory(libpq)
