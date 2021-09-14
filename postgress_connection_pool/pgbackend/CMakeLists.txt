project(pgbackend)

#include_directories(${PROJECT_SOURCE_DIR}/include)


#set(HEADER
#    ${PROJECT_SOURCE_DIR}/include/pgbackend/pgbackend.h
#)
set(SOURCE
    #${PROJECT_SOURCE_DIR}/src/pgbackend.cpp
    src/pgbackend.cpp
)



add_library(${PROJECT_NAME} ${SOURCE} )#STATIC ${HEADER}
add_library(sub::pgbackend ALIAS ${PROJECT_NAME})
#target_link_libraries(${PROJECT_NAME} pgconnection)
# This command attempts to find the library, REQUIRED argument is optional
find_package(PostgreSQL REQUIRED)
# Add include directories to your target. PRIVATE is useful with multi-target projects - see documentation of target_include_directories for more info
target_include_directories(${PROJECT_NAME}  PUBLIC ${PROJECT_SOURCE_DIR}/include ${PostgreSQL_INCLUDE_DIRS})
# Add libraries to link your target againts. Again, PRIVATE is important for multi-target projects
target_link_libraries(${PROJECT_NAME} PRIVATE ${PostgreSQL_LIBRARIES} pgconnection)

