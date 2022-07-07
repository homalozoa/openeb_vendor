cmake_minimum_required(VERSION 3.8)
project(openeb_vendor)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)

set(EXTPRJ_NAME openeb)
set(PKG_VER "3.0.2")
set(MD5SUM 42146e8de138e3dcfe25f0469a67f9c2)

include(ExternalProject)

externalproject_add(
  ${EXTPRJ_NAME}
  PREFIX ${EXTPRJ_NAME}
  URL https://github.com/prophesee-ai/openeb/archive/refs/tags/${PKG_VER}.tar.gz
  URL_MD5 ${MD5SUM}
  CMAKE_ARGS
      -DCMAKE_BUILD_TYPE=${CMAKE_BUILD_TYPE}
      -DCMAKE_INSTALL_PREFIX=${CMAKE_INSTALL_PREFIX}
      -DCOMPILE_PYTHON3_BINDINGS=OFF
      -DUDEV_RULES_SYSTEM_INSTALL=OFF
      -DBUILD_TESTING=OFF
  INSTALL_DIR ${CMAKE_INSTALL_PREFIX}
  TIMEOUT 1200
)

ament_package()
