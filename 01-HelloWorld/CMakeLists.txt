
# PYTHON_ADD_MODULE(hello hello.cpp)
PYTHON_ADD_AND_LINK_MODULE(hello hello.cpp)

# target_link_libraries(hello
#         ${Boost_LIBRARIES}
#         ${PYTHON_LIBRARIES}
#     )
FILE(COPY hello.py DESTINATION .)
ADD_TEST(01-HelloWorld hello.py)
