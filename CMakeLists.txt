cmake_minimum_required(VERSION 3.16)
project(expression_parser LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Основная библиотека парсера
add_library(expression_parser_lib
  src/ast.cpp
  src/tokenizer.cpp
  src/parser.cpp
  src/evaluator.cpp
  src/csv_writer.cpp
  src/thread_pool.cpp
)

target_include_directories(expression_parser_lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

# Исполняемый файл
add_executable(expression_parser src/main.cpp)
target_link_libraries(expression_parser PRIVATE expression_parser_lib)
target_include_directories(expression_parser PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)

# Поддержка многопоточности
find_package(Threads REQUIRED)
target_link_libraries(expression_parser PRIVATE Threads::Threads)
target_link_libraries(expression_parser_lib PUBLIC Threads::Threads)
