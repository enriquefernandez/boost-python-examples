
PYTHON_ADD_AND_LINK_MODULE(policies policies.cpp)
FILE(COPY policies.py DESTINATION .)
ADD_TEST(08-CallPolicies policies.py)

