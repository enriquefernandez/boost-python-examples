cmake_minimum_required(VERSION 2.8.3)
FIND_PACKAGE(PythonInterp)
FIND_PACKAGE(PythonLibs)
FIND_PACKAGE(Boost COMPONENTS python)

# CMake is not being able to find my homebrew python installation, therefore, I need to manually specify
SET(PYTHON_LIBRARIES /usr/local/Cellar/python/2.7.4/Frameworks/Python.framework/Versions/2.7/lib/libpython2.7.dylib)
SET(PYTHON_INCLUDE_DIRS /usr/local/Cellar/python/2.7.4/Frameworks/Python.framework/Versions/2.7/Headers)

MESSAGE("Python lib")
MESSAGE(${PYTHON_LIBRARIES})
MESSAGE("Python include dirs")
MESSAGE(${PYTHON_INCLUDE_DIRS})

ENABLE_TESTING()
INCLUDE_DIRECTORIES(${Boost_INCLUDE_DIRS} ${PYTHON_INCLUDE_DIRS})
# LINK_LIBRARIES(${Boost_LIBRARIES}) # Deprecated but so convenient!



# In OSX, need to explicitly link with python libraries
function(PYTHON_ADD_AND_LINK_MODULE _NAME )
	PYTHON_ADD_MODULE(${_NAME} ${ARGN})
	target_link_libraries(${_NAME} ${Boost_LIBRARIES} ${PYTHON_LIBRARIES})
	#target_link_libraries(${_NAME} ${Boost_LIBRARIES} /usr/local/Cellar/python/2.7.3/Frameworks/Python.framework/Versions/2.7/lib/libpython2.7.dylib)
	# target_link_libraries(${_NAME} ${Boost_LIBRARIES} /usr/local/Cellar/python/2.7.4/Frameworks/Python.framework/Versions/2.7/lib/libpython2.7.dylib)
	
endfunction()

ADD_SUBDIRECTORY(01-HelloWorld)
ADD_SUBDIRECTORY(02-ExposingClasses)
ADD_SUBDIRECTORY(03-Constructors)
ADD_SUBDIRECTORY(04-ClassMembers)
ADD_SUBDIRECTORY(05-Inheritance)
ADD_SUBDIRECTORY(06-VirtualFunctionsInPython)
ADD_SUBDIRECTORY(07-Operators)
ADD_SUBDIRECTORY(08-CallPolicies)
ADD_SUBDIRECTORY(09-Overloading)
ADD_SUBDIRECTORY(10-Embedding)
ADD_SUBDIRECTORY(11-Iterators)
ADD_SUBDIRECTORY(12-Exceptions)
ADD_SUBDIRECTORY(13-AutoInstantiation)

