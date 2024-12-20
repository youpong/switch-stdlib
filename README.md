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

C++ standard library に libc++ をリンクさせることを例にビルドの手順を説明します。
libstdc++ とリンクさせる場合には --with-cxx-standard-library オプションの値を
変えてください。

```
$ ./configure --with-cxx=clang++ --with-cxx-standard-library=libc++
$ make
```

## Test

```
$ make check
```
テストにパスするとその旨が表示されます。

# Docker

## Build Docker image `swlib`

```
$ docker build -t swlib .
```

## Create and run a new container from an image
```
$ docker run --rm -it -v $PWD:/swlib -w /swlib swlib 
```

# References

Linear congruential generator を実装する際に、特にパラメタの値について参照した。

Linear congruential generator
Wikipedia

https://en.wikipedia.org/wiki/Linear_congruential_generator#cite_note-LEcuyer99-10
