ExternalProject_Add(terminal-app
    DEPENDS material libpapyros
    GIT_REPOSITORY https://github.com/papyros/terminal-app.git
    GIT_TAG develop
    CMAKE_ARGS ${CMAKE_ARGS}
)

ExternalProject_Add(settings-app
    DEPENDS material libpapyros papyros-shell
    GIT_REPOSITORY https://github.com/papyros/settings-app.git
    GIT_TAG develop
    CMAKE_ARGS ${CMAKE_ARGS}
)

ExternalProject_Add(software-app
    DEPENDS material libpapyros
    GIT_REPOSITORY https://github.com/papyros/software-app.git
    CMAKE_ARGS ${CMAKE_ARGS}
)
