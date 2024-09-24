##########################
## Variables            ##
##########################

# Note: Variables can only be strings
# Note: Single or double quotes for variable names or values have no meaning ot Make

# CC: Proram for compiling C programs; default cc
# CFLAGS: Extra flags to give to the C Compiler
# CPPFLAGS: Extra flags to give to the C++ preprocessor
# LDFLAGS: Extra flags to give to the linker

DEBUG = 1
EXECUTABLE_NAME = main

CXX_STANDARD = c++17
CXX_WARNINGS = -Wall -Wextra -Wpedantic
CXX = g++
CXXFLAGS = $(CXX_WARNINGS) -std=$(CXX_STANDARD)
CPPFLAGS =
LDFLAGS =

ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
else
CXXFLAGS += -O3
endif

COMPILER_CALL = $(CXX) $(CXXFLAGS)

CXX_SOURCES =$(wildcard *.cc)
CXX_OBJECTS = $(patsubst %.cc, %.o, $(CXX_SOURCES))

##########################
## TARGETS              ##
##########################

build: $(CXX_OBJECTS)
	echo $(CXX_OBJECTS)
	$(COMPILER_CALL) $(CXX_OBJECTS) -o $(EXECUTABLE_NAME)

execute:
	./$(EXECUTABLE_NAME)

clean:
	rm -f *.o
	rm -f $(EXECUTABLE_NAME)


########################
## PATTERNS ##
########################
%.o: %.cc
	$(COMPILER_CALL) -c $< -o $@
