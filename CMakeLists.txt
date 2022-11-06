cmake_minimum_required(VERSION 3.23)
project(yaCADpro)

set(CMAKE_CXX_STANDARD 20)

include(cmake/FindOCC.cmake)

list(APPEND CMAKE_PREFIX_PATH "/opt/Qt/6.4.0/gcc_64")
find_package(Qt6 REQUIRED COMPONENTS Quick Gui)
qt_standard_project_setup()

include_directories(${OCC_INCLUDE_DIR})

qt_add_executable(app_yaCADpro main.cpp)
qt_add_qml_module(app_yaCADpro URI yaCADpro VERSION 1.0 QML_FILES qml/main.qml)

target_link_libraries(app_yaCADpro PRIVATE ${OCC_LIBRARIES} Qt6::Gui Qt6::Quick)
