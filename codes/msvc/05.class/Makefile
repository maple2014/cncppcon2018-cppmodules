# Define vars

CC = cl
CX = cl
LB = link
CFLAGS = /experimental:module /std:c++latest /EHsc /MD /c

# Compile

all: main

hello.ifc hello.obj: hello.ixx
	@echo Compiling $**...
	@$(CX) $(CFLAGS) $**

hello_impl.obj: hello.ifc hello_impl.cpp
	@echo Compiling $**...
	@$(CX) $(CFLAGS) /module:reference $**

main.obj: hello.ifc main.cpp
	@echo Compiling $**...
	@$(CX) $(CFLAGS) /module:reference $**

main: main.obj hello.obj hello_impl.obj
	@$(LB) $**

# Targets

clean:
	@echo Cleaning directorys...
	@del /f /q *.exe *.obj *.ifc
	@echo Clean complete.

# PHONY

.PHONY: all clean
