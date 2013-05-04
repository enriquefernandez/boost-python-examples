
PYTHON_ADD_AND_LINK_MODULE(operators operators.cpp)
FILE(COPY operators.py DESTINATION .)
ADD_TEST(07-Operators operators.py)

