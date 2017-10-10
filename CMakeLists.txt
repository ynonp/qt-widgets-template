cmake_minimum_required(VERSION 2.8.11)

project(testproject)

# Find includes in corresponding build directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)
# Instruct CMake to run moc automatically when needed.
set(CMAKE_AUTOMOC ON)

# Find the QtWidgets library
find_package(Qt5Widgets)

set(SOURCES
  src/main.cpp
  src/mainwindow.cpp
)

set(FORMS
  forms/mainwindow.ui
)
qt5_wrap_ui(FORM_H ${FORMS})

# Tell CMake to create the helloworld executable
add_executable(helloworld ${SOURCES} ${FORM_H})

# Use the Widgets module from Qt 5.
target_link_libraries(helloworld Qt5::Widgets)

