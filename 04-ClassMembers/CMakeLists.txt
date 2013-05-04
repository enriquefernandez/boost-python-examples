
PYTHON_ADD_AND_LINK_MODULE(member member.cpp)
FILE(COPY member.py DESTINATION .)
ADD_TEST(04-ClassMembers member.py)

