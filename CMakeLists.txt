project(papyros)

cmake_minimum_required(VERSION 3.0.0 FATAL_ERROR)

include(ExternalProject)

set(CMAKE_ARGS
    -DCMAKE_INSTALL_PREFIX=${CMAKE_INSTALL_PREFIX}
    -DLIB_INSTALL_DIR=lib
    -DLIBEXEC_INSTALL_DIR=lib
    -DQML_INSTALL_DIR=lib/qt/qml
)

ExternalProject_Add(libpapyros
    GIT_REPOSITORY https://github.com/papyros/libpapyros.git
    GIT_TAG develop
    CMAKE_ARGS ${CMAKE_ARGS}
)

ExternalProject_Add(material
    GIT_REPOSITORY https://github.com/papyros/qml-material.git
    GIT_TAG develop
    CMAKE_ARGS ${CMAKE_ARGS}
)

ExternalProject_Add(greenisland
    GIT_REPOSITORY https://github.com/greenisland/greenisland.git
    CMAKE_ARGS ${CMAKE_ARGS}
)

ExternalProject_Add(papyros-shell
    DEPENDS greenisland
    GIT_REPOSITORY https://github.com/papyros/papyros-shell.git
    GIT_TAG develop
    CMAKE_ARGS ${CMAKE_ARGS}
)

add_subdirectory(core-apps)
