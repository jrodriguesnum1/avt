# makefile to compile projects on the lab
CC = g++
CFLAGS = -ansi -Wall -pedantic

DEPSDIR = ../../dependencies
DEPS_DIR = $(DEPSDIR)/debian6

INCLUDES = -I$(DEPS_DIR)/glew/include
LIB_FILE = -L$(DEPS_DIR)/glew/lib

LIBS = -lGL -lGLEW -lglut -lGLU

SRCSDIR = src
SRCS = $(shell cd $(SRCSDIR); find . -name "*.cpp")
OBJSDIR = objs
OBJS = $(SRCS:%.cpp=%.o)
OBJS_WITH_DIR = $(OBJS:./%.o=$(OBJSDIR)/%.o)
RELEASEDIR = $(OBJSDIR)/Release
DEBUGDIR = $(OBJSDIR)/Debug
BINDIR = bin

release: $(OBJS_WITH_DIR)
	$(CC) $(CFLAGS) $(INCLUDES) $(LIB_FILE) -o $(BINDIR)/$(EXE) $(OBJS_WITH_DIR) $(LIBS);

$(OBJSDIR)/%.o: $(SRCSDIR)/%.cpp
	g++ $(CFLAGS) -c $< -o $@ $(INCLUDES)
