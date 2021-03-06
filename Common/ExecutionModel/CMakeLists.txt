SET(Module_SRCS
  vtkAlgorithm.cxx
  vtkAlgorithmOutput.cxx
  vtkAnnotationLayersAlgorithm.cxx
  vtkArrayDataAlgorithm.cxx
  vtkCachedStreamingDemandDrivenPipeline.cxx
  vtkCastToConcrete.cxx
  vtkCompositeDataPipeline.cxx
  vtkCompositeDataSetAlgorithm.cxx
  vtkDataObjectAlgorithm.cxx
  vtkDataSetAlgorithm.cxx
  vtkDemandDrivenPipeline.cxx
  vtkDirectedGraphAlgorithm.cxx
  vtkEnsembleSource.cxx
  vtkExecutive.cxx
  vtkExtentSplitter.cxx
  vtkExtentTranslator.cxx
  vtkFilteringInformationKeyManager.cxx
  vtkGraphAlgorithm.cxx
  vtkHierarchicalBoxDataSetAlgorithm.cxx
  vtkHyperTreeGridAlgorithm.cxx
  vtkImageAlgorithm.cxx
  vtkImageInPlaceFilter.cxx
  vtkImageProgressIterator.cxx
  vtkImageToStructuredGrid.cxx
  vtkImageToStructuredPoints.cxx
  vtkInformationDataObjectMetaDataKey.cxx
  vtkInformationExecutivePortKey.cxx
  vtkInformationExecutivePortVectorKey.cxx
  vtkInformationIntegerRequestKey.cxx
  vtkMultiBlockDataSetAlgorithm.cxx
  vtkMultiTimeStepAlgorithm.cxx
  vtkPassInputTypeAlgorithm.cxx
  vtkPiecewiseFunctionAlgorithm.cxx
  vtkPiecewiseFunctionShiftScale.cxx
  vtkPointSetAlgorithm.cxx
  vtkPolyDataAlgorithm.cxx
  vtkRectilinearGridAlgorithm.cxx
  vtkScalarTree.cxx
  vtkSimpleImageToImageFilter.cxx
  vtkSimpleScalarTree.cxx
  vtkSpanSpace.cxx
  vtkSphereTree.cxx
  vtkStreamingDemandDrivenPipeline.cxx
  vtkStructuredGridAlgorithm.cxx
  vtkTableAlgorithm.cxx
  vtkSMPProgressObserver.cxx
  vtkThreadedCompositeDataPipeline.cxx
  vtkThreadedImageAlgorithm.cxx
  vtkTreeAlgorithm.cxx
  vtkTrivialConsumer.cxx
  vtkTrivialProducer.cxx
  vtkUndirectedGraphAlgorithm.cxx
  vtkUnstructuredGridAlgorithm.cxx
  vtkUnstructuredGridBaseAlgorithm.cxx
  vtkProgressObserver.cxx
  vtkSelectionAlgorithm.cxx
  vtkExtentRCBPartitioner.cxx
  vtkUniformGridPartitioner.cxx
  # New AMR classes
  vtkUniformGridAMRAlgorithm.cxx
  vtkOverlappingAMRAlgorithm.cxx
  vtkNonOverlappingAMRAlgorithm.cxx
  )


if (NOT VTK_LEGACY_REMOVE)
  list(APPEND Module_SRCS
    vtkHyperOctreeAlgorithm.cxx
  )
endif()

set_source_files_properties(
  vtkExecutionSchedulerManager
  vtkFilteringInformationKeyManager
  vtkImageProgressIterator
  vtkSMPProgressObserver
  WRAP_EXCLUDE
  )

vtk_module_library(vtkCommonExecutionModel ${Module_SRCS})
