cmake_minimum_required(VERSION 3.5)

project(PreGraphic VERSION 0.1 LANGUAGES CXX)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# set(CMAKE_PREFIX_PATH "/Users/margaret/Qt/6.7.2/macos/lib/cmake")
find_package(QT NAMES Qt6 Qt5 REQUIRED COMPONENTS Widgets)
find_package(Qt${QT_VERSION_MAJOR} REQUIRED COMPONENTS Widgets)
find_package(Qt6 REQUIRED COMPONENTS Widgets Concurrent)
find_package(Qt6 COMPONENTS Widgets Charts REQUIRED)


set(PROJECT_SOURCES
        main.cpp
        mainwindow.cpp
        mainwindow.h
        mainwindow.ui
)


add_executable(PreGraphic
    ${PROJECT_SOURCES}
)


target_link_libraries(PreGraphic PRIVATE Qt6::Widgets
                                      Qt6::Concurrent
                                      )
target_link_libraries(PreGraphic PRIVATE Qt6::Widgets
                                                 Qt6::Charts)

qt_finalize_executable(PreGraphic)


