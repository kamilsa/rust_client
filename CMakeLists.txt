cmake_minimum_required(VERSION 3.13)
project(rust_client)

set(CMAKE_CXX_STANDARD 17)

enable_testing()
add_subdirectory(client)

set(SOURCE main.cpp)
#get_target_property(CLIENT_DIR client LOCATION)

add_executable(main ${SOURCE})
target_link_libraries(main ${CLIENT_DIR}/libclient.dylib)
add_dependencies(main client)
