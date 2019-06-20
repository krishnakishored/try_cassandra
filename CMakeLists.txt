cmake_minimum_required(VERSION 3.12)

project(TryCassandra
        VERSION 1.0.0
        DESCRIPTION "A simple c++ app that uses cassandra-cpp-driver")

set(CMAKE_POSITION_INDEPENDENT_CODE ON)        

# option()

add_subdirectory(external)
# order of add_subdirectory # is it important???
# make[2]: *** No rule to make target `external/cpp-driver/libcassandra.2.12.0.dylib', needed by `app/trycassandra
add_subdirectory(app) 



