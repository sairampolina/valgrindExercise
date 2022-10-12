# C++ Boilerplate
[![Build Status](https://travis-ci.org/dpiet/cpp-boilerplate.svg?branch=master)](https://travis-ci.org/dpiet/cpp-boilerplate)
[![Coverage Status](https://coveralls.io/repos/github/dpiet/cpp-boilerplate/badge.svg?branch=master)](https://coveralls.io/github/dpiet/cpp-boilerplate?branch=master)
---

## Overview
The Code contains two bugs which lead to a memory leak, this issue was rectified using Valgrind

## Setting up Repository
```
git clone -b valgrind_exercise https://github.com/thedancomplex/cpp-boilerplate.git
cd <path to repository>
mkdir build
cd build
cmake ..
make
Run tests: ./test/cpp-test
Run program: ./app/shell-app
```
## Valgrind
```
sudo apt install valgrind
cd build
valgrind --leak-check=full -v ./app/shell-app >& ../results/valgrind_rectified_result.txt
```

## KCachegrind
```
sudo apt-get install -y kcachegrind
cd build
valgrind --tool=callgrind  ./app/shell-app
kcachegrind
```
Open the ```callgrind.out.xxxx``` file in the GUI.


## Building for code coverage
```
sudo apt-get install lcov
cmake -D COVERAGE=ON -D CMAKE_BUILD_TYPE=Debug ../
make
make code_coverage
