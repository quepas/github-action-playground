cmake_minimum_required( VERSION 3.0 )

project( pep2csv-project VERSION 1.0 )

set( CMAKE_CXX_STANDARD 17 )
set( CMAKE_BUILD_TYPE Debug )
set( CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin/ )

# Add and build ANTLR parser generator
set( ANTLR_CPP_DIR third-party/antlr4/runtime/Cpp/ )
add_subdirectory( ${ANTLR_CPP_DIR} )
include_directories( ${ANTLR_CPP_DIR}/runtime/src )

add_executable( pep2csv
        src/main.cpp )
target_link_libraries( pep2csv antlr4_static )
