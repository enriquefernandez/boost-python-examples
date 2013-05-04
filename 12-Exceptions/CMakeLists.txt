
PYTHON_ADD_AND_LINK_MODULE(myexceptions myexceptions.cpp)
FILE(COPY myexceptions.py DESTINATION .)
ADD_TEST(12-Exceptions myexceptions.py)

