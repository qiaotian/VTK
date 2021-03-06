include(vtkObjectFactory)

set(Module_SRCS
  vtkPLagrangianParticleTracker.cxx
  vtkPTemporalStreamTracer.cxx
  vtkPStreamTracer.cxx
  vtkPParticleTracer.cxx
  vtkPParticlePathFilter.cxx
  vtkPStreaklineFilter.cxx
  vtkPParticleTracerBase.cxx
  )

# Overrides for object factory.
set(parallel_overrides
  LagrangianParticleTracker
  StreamTracer
  TemporalStreamTracer
  ParticleTracer
  ParticlePathFilter
  StreaklineFilter
  )

foreach(_override ${parallel_overrides})
  vtk_add_override(vtk${_override} vtkP${_override})
endforeach()
vtk_object_factory_configure("${vtk_module_overrides}")
list(APPEND Module_SRCS
  ${CMAKE_CURRENT_BINARY_DIR}/${vtk-module}ObjectFactory.cxx)
set_source_files_properties(
  ${vtk-module}ObjectFactory.cxx
  PROPERTIES
    WRAP_EXCLUDE 1
    WRAP_EXCLUDE_PYTHON 1
  )

vtk_module_library(vtkFiltersParallelFlowPaths ${Module_SRCS})
