cmake_minimum_required(VERSION 3.16)
project(SnakeGame)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src)

find_package(Qt6 COMPONENTS Widgets REQUIRED)

set(SOURCE_FILES
    main.cpp
    src/game.cpp
    src/game.h
    src/snake.cpp
    src/snake.h
    src/map.cpp
    src/map.h
    src/obstacle.cpp
    src/obstacle.h
    resources/map1.txt
    resources/map2.txt
    resources/map3.txt
    resources/map4.txt
)

set(RESOURCE_FILES
    resources/map1.txt
    resources/map2.txt
    resources/map3.txt
    resources/map4.txt
)

add_executable(SnakeGame ${SOURCE_FILES})
target_link_libraries(SnakeGame Qt6::Widgets)

install(TARGETS SnakeGame DESTINATION bin)
install(FILES ${RESOURCE_FILES} DESTINATION resources)
