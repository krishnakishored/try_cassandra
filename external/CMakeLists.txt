cmake_minimum_required(VERSION 3.12)

if(THRIDPARTY_USE_CASSANDRA_DRIVER)
  find_package(cpp-driver 2.11 REQUIRED)
else()
  add_subdirectory(cpp-driver)
endif()