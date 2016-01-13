cmake_minimum_required(VERSION 3.2)

include("cmake/hunter/cmake/HunterGate.cmake")

HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.12.34.tar.gz"
    SHA1 "13fe1a17d8f4d1c0f4652fa2453ea2ae708622c4" )

project(HunterTest)

hunter_add_package(Boost COMPONENTS regex system filesystem)

find_package(Boost CONFIG REQUIRED regex system filesystem)

add_executable(hunter_test src/main.cpp)
target_link_libraries(hunter_test PUBLIC Boost::regex Boost::system Boost::filesystem)

