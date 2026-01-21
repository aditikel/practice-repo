cxx = g++
flag = -g -Wall -std=c++17
GTEST_DIR = /opt/homebrew/opt/googletest
GTEST_INC = -I$(GTEST_DIR)/include
GTEST_LIB = -L$(GTEST_DIR)/lib -lgtest -lgtest_main -pthread

all: test

run: test
	./test

library.o: library.cpp library.hpp
	$(cxx) $(flag) library.cpp -c -o library.o

test: test.cpp library.o
	$(cxx) $(flag) $(GTEST_INC) test.cpp library.o $(GTEST_LIB) -o test

.PHONY: clean
clean:
	rm *.o test
