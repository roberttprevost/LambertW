
cmake_minimum_required(VERSION 2.8.12)
project(LambertW)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

# add library
set(SOURCE FukushimaLambertW.cc LambertW.cc)
set(HEADERS FukushimaLambertW.h LambertW.h Horner.h)
add_library(LambertW STATIC ${SOURCE} ${HEADERS}) 
set_target_properties(LambertW PROPERTIES LINKER_LANGUAGE CXX)

# add executables
add_executable(lambertw lambertw.cxx)
target_link_libraries(lambertw LambertW)

add_executable(test_accuracy test_accuracy.cxx)
target_link_libraries(test_accuracy LambertW)

#CMakeLists.txt        Horner.h      LambertW.h          README.md
#FukushimaLambertW.cc  LambertW.cc   LICENSE-BSD-2C.txt  test_accuracy.cxx
#FukushimaLambertW.h   lambertw.cxx  LICENSE-GPL-v2.txt

