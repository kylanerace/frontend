cmake_minimum_required(VERSION 2.9)
project(hebench_reportgen)

set(${PROJECT_NAME}_SOURCES
    "${CMAKE_CURRENT_SOURCE_DIR}/src/hebench_report_utils.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/hebench_report_impl.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/hebench_report.cpp"
    )
set(${PROJECT_NAME}_HEADERS
    "${CMAKE_CURRENT_SOURCE_DIR}/include/hebench_report_utils.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/include/hebench_report_impl.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/../include/hebench_report_types.h"
    "${CMAKE_CURRENT_SOURCE_DIR}/../include/hebench_report.h"
    )

add_library(${PROJECT_NAME} SHARED ${${PROJECT_NAME}_SOURCES} ${${PROJECT_NAME}_HEADERS})

target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../include)
target_compile_options(${PROJECT_NAME} PRIVATE -Wall -Wextra)

install(TARGETS ${PROJECT_NAME} DESTINATION lib)
