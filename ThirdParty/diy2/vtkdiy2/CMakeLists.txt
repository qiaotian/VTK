project(diy2)

if (NOT VTK_INSTALL_NO_DEVELOPMENT)
  install(
    DIRECTORY   "${CMAKE_CURRENT_SOURCE_DIR}/include/vtkdiy"
    DESTINATION "${VTK_INSTALL_INCLUDE_DIR}"
    COMPONENT   Development)
endif ()
