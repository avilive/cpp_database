project(pgconnection)

#include_directories(${PROJECT_SOURCE_DIR}/include )
#message(SEND_MESSAGE ${PostgreSQL_INCLUDE_DIRS})

#target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/include/pgconnection)
include_directories(${PROJECT_SOURCE_DIR}/include/pgconnection)
set(HEADER
    ${PROJECT_SOURCE_DIR}/include/pgconnection/pgconnection.h
    ${PostgreSQL_INCLUDE_DIRS}/
)

set(SOURCE
    ${PROJECT_SOURCE_DIR}/src/pgconnection.cpp
)
add_library(${PROJECT_NAME} STATIC ${HEADER} ${SOURCE} )
add_library(sub::pgconnection ALIAS ${PROJECT_NAME})

# This command attempts to find the library, REQUIRED argument is optional
find_package(PostgreSQL REQUIRED)
# Add include directories to your target. PRIVATE is useful with multi-target projects - see documentation of target_include_directories for more info
target_include_directories(${PROJECT_NAME}  PRIVATE ${PostgreSQL_INCLUDE_DIRS})
# Add libraries to link your target againts. Again, PRIVATE is important for multi-target projects
target_link_libraries(${PROJECT_NAME} PRIVATE ${PostgreSQL_LIBRARIES})
target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/include/pgconnection)


