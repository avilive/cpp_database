project(libpq)

include_directories(${PROJECT_SOURCE_DIR}/include)

set(SOURCE
    ${PROJECT_SOURCE_DIR}/include/libpq/libpq-fe.h
    ${PROJECT_SOURCE_DIR}/include/pg_config/pg_config_ext.h
    ${PROJECT_SOURCE_DIR}/include/postgres_ext/postgres_ext.h
)

add_library(${PROJECT_NAME} STATIC ${SOURCE})
target_link_libraries(${PROJECT_NAME} pgconnection)
target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/include/libpq)
target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/include/pg_config)
target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/include/postgres_ext)