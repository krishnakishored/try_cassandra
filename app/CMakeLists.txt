cmake_minimum_required(VERSION 3.12)

project(App
        VERSION 1.0.0
        DESCRIPTION "A simple c++ app that uses cpp-cassandra-driver")


add_executable(trycassandra)  
target_sources(trycassandra PRIVATE runner.cpp)
target_compile_features(trycassandra PRIVATE cxx_std_14)

# Note that the namespaced target will always be available regardless of the import method
# find_library(
#        NAMES  libcassandra.2.12.0.dylib libcassandra.2.dylib libcassandra.dylib,
#        HINTS ../external

# )

# Note that the namespaced target will always be available regardless of the import method

# Your-external "mylib", add GLOBAL if the imported library is located in directories above the current.
# add_library(libcassandra.2.12.0.dylib SHARED IMPORTED GLOBAL )
add_library(libcassandra SHARED IMPORTED)
# You can define two import-locations: one for debug and one for release.
set_target_properties( libcassandra PROPERTIES IMPORTED_LOCATION ${CMAKE_BINARY_DIR}/external/cpp-driver/libcassandra.2.12.0.dylib)
target_link_libraries(trycassandra libcassandra)
