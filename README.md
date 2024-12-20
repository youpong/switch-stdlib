# README

This project is a C++ example project. It allows you to choose the implementation of
the C++ standard library to link from libstdc++ of the GNU project and libc++ of the LLVM project.

* Requisite

This project is written in C++20, you will need a recent version of a C++ compiler and
C++ standard library. 

# Tested Environment

We are testing in the following environments:

* macOS 15.2
  * Xcode 16.2 (using the bundled Apple Clang 16.0.0)
* Ubuntu 24.04.1 LTS
  * GCC 13.3.0
  * Clang 18.1.3

## How to Build

The following build procedure is described using the example of linking with libc++.
If you want to link with libstdc++, change the value of the --with-cxx-standard-library
option.
Descriptions of the `configure` scripts are available with the --help option.

```
$ ./configure --with-cxx=clang++ --with-cxx-standard-library=libc++
$ make
```

## Test

The output of the following command shows the results of the test.

```
$ make check
```

# Docker

## Build Docker image `swlib`

```
$ docker build -t swlib .
```

## Create and run a new container from an image
```
$ docker run --rm -it -v $PWD:/swlib -w /swlib swlib 
```

# License

MIT
