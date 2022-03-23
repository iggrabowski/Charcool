cmake_minimum_required(VERSION "3.23.0")

project(Charcool)

set(SFML_STATIC_LIBRARIES TRUE)

find_package(SFML 2.5 COMPONENTS system window graphics REQUIRED)

add_executable("${PROJECT_NAME}" "main.cpp")

target_link_libraries("${PROJECT_NAME}" sfml-system sfml-window sfml-graphics)

install(TARGETS "${PROJECT_NAME}" DESTINATION bin)
install(FILES "main.cpp" DESTINATION src)

include(CTest)

add_test("test1" "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}")

include(CPack)