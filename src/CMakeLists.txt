FILE(GLOB_RECURSE SOURCES "*.cpp")
FILE(GLOB_RECURSE HEADERS "*.h")

IF(CMAKE_GENERATOR MATCHES "Xcode")
  add_executable(SimpleIRGenerator ${SOURCES} ${HEADERS})
ELSE()
  add_executable(SimpleIRGenerator ${SOURCES})
ENDIF()

target_link_libraries(SimpleIRGenerator PRIVATE ${llvm_libs})
