find_program(PYTHON "python")

if (PYTHON)
  message("Running setup.py for urdf_parser_py")
  set(SETUP_PY "${CMAKE_CURRENT_SOURCE_DIR}/setup.py")
  install(CODE "execute_process(COMMAND \"${PYTHON}\" \"${SETUP_PY}\" build --build-base \"${CMAKE_CURRENT_BINARY_DIR}/pybuild\" install --install-layout deb --prefix \"${CMAKE_INSTALL_PREFIX}\"
                WORKING_DIRECTORY \"${CMAKE_CURRENT_SOURCE_DIR}\")")
endif()
