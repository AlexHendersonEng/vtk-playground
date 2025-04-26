# Add executable
add_executable(CylinderExample main.cpp)

# Add VTK libraries
target_link_libraries(CylinderExample PRIVATE ${VTK_LIBRARIES})

# Copy VTK DLLs to the output directory
add_custom_command(TARGET CylinderExample POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E copy_directory
    ${VTK_DLL_DIR}
    $<TARGET_FILE_DIR:CylinderExample>)

# vtk_module_autoinit is needed
vtk_module_autoinit(
  TARGETS CylinderExample
  MODULES ${VTK_LIBRARIES}
)