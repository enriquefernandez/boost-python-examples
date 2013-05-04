
PYTHON_ADD_AND_LINK_MODULE(mymodule mymodule.cpp)
ADD_EXECUTABLE(embedding mymodule.cpp embedding.cpp)
TARGET_LINK_LIBRARIES(embedding ${Boost_LIBRARIES} ${PYTHON_LIBRARIES})
FILE(COPY embedding.py DESTINATION .)
ADD_TEST(10-Embedding embedding)

