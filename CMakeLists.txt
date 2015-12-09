cmake_minimum_required (VERSION 2.8.0)
project ("ZPar - A collections of sentence parsing tools")
set (EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
set (SOURCE_DIR             ${PROJECT_SOURCE_DIR}/src)
include_directories (${SOURCE_DIR} ${SOURCE_DIR}/include)
include_directories (${SOURCE_DIR}/chinese)
set (CMAKE_CXX_FLAGS "-std=c++11 -g -w -W -O3 -DNDEBUG -DPERCEPTRON_FOR_DECODING -DTARGET_LANGUAGE=chinese")
include_directories (${SOURCE_DIR}/chinese/conparser)
include_directories (${SOURCE_DIR}/chinese/conparser/implementations/jcad)
add_executable (chinese.conparser.parser
${SOURCE_DIR}/libs/reader.cpp
${SOURCE_DIR}/libs/writer.cpp
${SOURCE_DIR}/libs/options.cpp
${SOURCE_DIR}/libs/linguistics/lemma.cpp
${SOURCE_DIR}/libs/linguistics/conll.cpp
${SOURCE_DIR}/libs/learning/dbn.cpp
${SOURCE_DIR}/libs/linguistics/constituent.cpp
${SOURCE_DIR}/libs/linguistics/jointconstituent.cpp
${SOURCE_DIR}/chinese/conparser/implementations/jcad/conparser.cpp
${SOURCE_DIR}/chinese/conparser/implementations/jcad/weight.cpp
${SOURCE_DIR}/chinese/conparser/main.cpp
)
set (CMAKE_CXX_FLAGS "-std=c++11 -g -w -W -O3 -DNDEBUG -DTARGET_LANGUAGE=chinese")
add_executable (chinese.conparser.train
${SOURCE_DIR}/libs/reader.cpp
${SOURCE_DIR}/libs/writer.cpp
${SOURCE_DIR}/libs/options.cpp
${SOURCE_DIR}/libs/linguistics/lemma.cpp
${SOURCE_DIR}/libs/linguistics/conll.cpp
${SOURCE_DIR}/libs/learning/dbn.cpp
${SOURCE_DIR}/libs/linguistics/constituent.cpp
${SOURCE_DIR}/libs/linguistics/jointconstituent.cpp
${SOURCE_DIR}/chinese/conparser/implementations/jcad/conparser.cpp
${SOURCE_DIR}/chinese/conparser/implementations/jcad/weight.cpp
${SOURCE_DIR}/chinese/conparser/train.cpp
)
