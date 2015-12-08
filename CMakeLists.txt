cmake_minimum_required (VERSION 2.8.0)
project ("ZPar - A collections of sentence parsing tools")
set (EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
set (SOURCE_DIR             ${PROJECT_SOURCE_DIR}/src)
include_directories (${SOURCE_DIR} ${SOURCE_DIR}/include)
include_directories (${SOURCE_DIR}/english)
set (CMAKE_CXX_FLAGS "-std=c++11 -g -w -W -O3 -DNDEBUG -DPERCEPTRON_FOR_DECODING -DLABELED -DTARGET_LANGUAGE=english")
include_directories (${SOURCE_DIR}/common/depparser)
include_directories (${SOURCE_DIR}/common/depparser/implementations/arceager)
add_executable (english.depparser.parser
${SOURCE_DIR}/libs/reader.cpp
${SOURCE_DIR}/libs/writer.cpp
${SOURCE_DIR}/libs/options.cpp
${SOURCE_DIR}/libs/linguistics/lemma.cpp
${SOURCE_DIR}/libs/linguistics/conll.cpp
${SOURCE_DIR}/libs/learning/dbn.cpp
${SOURCE_DIR}/common/depparser/implementations/arceager/depparser.cpp
${SOURCE_DIR}/common/depparser/implementations/arceager/depparser_weight.cpp
${SOURCE_DIR}/common/depparser/main.cpp
)
set (CMAKE_CXX_FLAGS "-std=c++11 -g -w -W -O3 -DNDEBUG -DLABELED -DTARGET_LANGUAGE=english")
add_executable (english.depparser.train
${SOURCE_DIR}/libs/reader.cpp
${SOURCE_DIR}/libs/writer.cpp
${SOURCE_DIR}/libs/options.cpp
${SOURCE_DIR}/libs/linguistics/lemma.cpp
${SOURCE_DIR}/libs/linguistics/conll.cpp
${SOURCE_DIR}/libs/learning/dbn.cpp
${SOURCE_DIR}/common/depparser/implementations/arceager/depparser.cpp
${SOURCE_DIR}/common/depparser/implementations/arceager/depparser_weight.cpp
${SOURCE_DIR}/common/depparser/train.cpp
)
