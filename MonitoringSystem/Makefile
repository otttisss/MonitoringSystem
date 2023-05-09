.PHONY: all install uninstall dist clean dvi tests

SOURCES = view/*.cc agents/*.cc controller/*.cc
HEADERS = view/*.h agents/*.h controller/*.h

build: 
		cmake -S . -B ./build
		cmake --build ./build

install: build

		cp -rf ./build/MonitoringSystem.app $(HOME)/Applications/

uninstall:

		rm -rf $(HOME)/Applications/MonitoringSystem.app

clean:
		rm -rf ./build
		rm -rf test

style:
		clang-format -n -style=Google $(SOURCES) $(HEADERS)

dist:	clean
		tar -czf MLP.tgz ./*

dvi:
		open readme.pdf

# tests: clean
# 		g++ -std=c++17 -lgtest logic/tests/test.cpp logic/*.cpp -o test