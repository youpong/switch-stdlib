# swtch-stdlib

This project is a C++ example designed to demonstrate flexibility in linking different
implementations of the C++ standard library. You can choose between `libstdc++`,
provided by the GNU project, and `libc++`, developed by the LLVM project.

The project also includes a `Dockerfile` that can be used to build/test.

## Requisite

This project is written in C++20, you will need a recent version of a C++ compiler and
C++ standard library. 

## Tested Environment

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

## Setting Up a Docker Environment for Build/Test

This project supports building and testing within a Docker container. The process mirrors the standard
build/test procedure, ensuring consistency across environments.

### Key Points
- The Docker image is based on `Ubuntu`.
- Building and testing inside the container follow the same steps as running directly on a native system.

### Steps

#### Build Docker image `swlib`

```
$ docker build -t swlib .
```

#### Create and run a new container from an image

```
$ docker run --rm -it -v $PWD:/swlib -w /swlib swlib 
```

## License

MIT
