cmake_minimum_required(VERSION 3.9)
project(SFMLClion)

set(CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -std=c++14 -static")
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_PREFIX_PATH K:/GameProgrammingEnv/ExternalLibs/SFML-2.4.2/lib)

add_executable(SFMLClion main.cpp)
set(SFML_STATIC_LIBRARIES TRUE)

# Detect and add SFML
set(SFML_DIR "K:/GameProgrammingEnv/ExternalLibs/SFML-2.4.2/share/SFML/cmake/Modules")
set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake_modules" ${CMAKE_MODULE_PATH})
#Find any version 2.X of SFML
#See the FindSFML.cmake file for additional details and instructions
find_package(SFML 2 COMPONENTS audio graphics window system REQUIRED)
if(SFML_FOUND)
    include_directories(${SFML_INCLUDE_DIR})
    target_link_libraries(SFMLClion ${SFML_LIBRARIES} ${SFML_DEPENDENCIES})
endif()

