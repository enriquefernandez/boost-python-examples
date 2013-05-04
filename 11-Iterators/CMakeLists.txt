
PYTHON_ADD_AND_LINK_MODULE(iterators iterators.cpp)
FILE(COPY iterators.py DESTINATION .)
ADD_TEST(11-Iterators iterators.py)

