add_mlir_dialect_library(MLIRLLVMIR
  IR/LLVMDialect.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Dialect/LLVMIR

  DEPENDS
  MLIRControlFlowInterfacesIncGen
  MLIRLLVMOpsIncGen
  MLIRLLVMConversionsIncGen
  )
target_link_libraries(MLIRLLVMIR
  PUBLIC
  LLVMAsmParser
  LLVMCore
  LLVMSupport
  LLVMFrontendOpenMP
  MLIRAnalysis
  MLIROpenMP
  MLIRIR
  MLIRSupport
  )

add_mlir_dialect_library(MLIRNVVMIR
  IR/NVVMDialect.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Dialect/LLVMIR

  DEPENDS
  MLIRNVVMOpsIncGen
  MLIRNVVMConversionsIncGen
  )
target_link_libraries(MLIRNVVMIR
  PUBLIC
  LLVMAsmParser
  MLIRIR
  MLIRLLVMIR
  LLVMSupport
  LLVMCore
  )

add_mlir_dialect_library(MLIRROCDLIR
  IR/ROCDLDialect.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/Dialect/LLVMIR

  DEPENDS
  MLIRROCDLOpsIncGen
  MLIRROCDLConversionsIncGen
  )
target_link_libraries(MLIRROCDLIR
  PUBLIC
  LLVMAsmParser
  LLVMCore
  LLVMSupport
  MLIRIR
  )
