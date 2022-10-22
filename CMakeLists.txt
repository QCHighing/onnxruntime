cmake_minimum_required(VERSION 3.20)

project(onnxruntime)

set(CMAKE_CXX_STANDARD 17)

add_library(${PROJECT_NAME} INTERFACE IMPORTED GLOBAL)
target_include_directories(
  ${PROJECT_NAME}
  INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/include
  INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/include/core)
target_link_libraries(
  ${PROJECT_NAME}
  INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/libonnxruntime_providers_cuda.so
            ${CMAKE_CURRENT_SOURCE_DIR}/libonnxruntime.so
            ${CMAKE_CURRENT_SOURCE_DIR}/libonnxruntime_providers_shared.so)
