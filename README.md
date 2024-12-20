# README

このプロジェクトは C++ のサンプルプロジェクトです。リンクする C++ 標準ライブラリを GNU プロジェクトの libstdc++ と LLVM プロジェクトの libc++から選択できるようにしています。

* Requisite

written in C++20, you will need a recent version of a C++ compiler and C++ standard 
library. 

# Tested Environment

macOS と Linux でテストしている。より詳細には以下の通り。

* macOS 15.2
* Xcode 16.2
* Apple clang 16.0.0

* Ubuntu 24.04.1 LTS
* gcc 13.3.0
* clang 18.1.3

## Build

```
$ make 
```

## Test

```
$ make check
```


# Docker

## Build Docker image `random`

```
$ docker build -t random .
```

## Create and run a new container from an image
```
$ docker run --rm -it -v $PWD:/random -w /random random 
```

# References

Linear congruential generator を実装する際に、特にパラメタの値について参照した。

Linear congruential generator
Wikipedia

https://en.wikipedia.org/wiki/Linear_congruential_generator#cite_note-LEcuyer99-10
