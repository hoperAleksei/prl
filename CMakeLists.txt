cmake_minimum_required(VERSION 3.16)
project(ParallelProgramming)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_COMPILER /usr/bin/g++-10)
set(GCC_COMPILE_FLAGS "-fopenmp -std=gnu++2a -m64")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${GCC_COMPILE_FLAGS}")

set(HELPERS
        helper/partial_sum.h
        helper/tester.h
        helper/vector.h
        helper/threads.h helper/threads.cpp
        helper/barrier.h helper/barrier.cpp
        helper/lut.h helper/lut.cpp)

set(LAB1
        lab1/cs.h lab1/cs.cpp
        lab1/atomic.h lab1/atomic.cpp
        lab1/average.h lab1/average.cpp
        lab1/fs.h lab1/fs.cpp)

set(LAB2
        lab2/randomizer.h lab2/randomizer.cpp)

set(LAB3
        lab3/fibonacci.h lab3/fibonacci.cpp)

add_executable(lab_1 lab1/lab1.cpp ${LAB1} ${HELPERS})
add_executable(lab_2 lab2/lab2.cpp ${LAB2} ${HELPERS})
add_executable(lab_3 lab3/lab3.cpp ${LAB3} ${HELPERS})