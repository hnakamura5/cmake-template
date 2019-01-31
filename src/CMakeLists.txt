set(CPP_FILES main.cpp)

add_executable(template_executable ${CPP_FILES})
install(TARGETS template_executable DESTINATION ${INSTALL_DIR})
