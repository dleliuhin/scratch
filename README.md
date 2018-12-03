# Scratch C++ Project template

Hi, this is a very simple C++ template I created to have a starting point for my ideas.
It provides a basic yet functioning setup of CMake, CTest, GoogleTest as well as Doxygen.

If you find it useful, great! If you have ideas, suggestions or found a bug then please open an
issue or make a pull request.

The way I organized this template is by no way mandatory and I've kept it minimal for that reason.
It should be easy to add, drop or rearange parts to your liking :).

Also I do not claim to follow all best practices. Like said above, I'm open for suggestions.

Cheers, Rafael

## Project overview

What is included :

* Directory layout of a project consisting of an executable, a static library and a shared library.
    * Rudimentary and nonsensical code serving as placeholder for these targets.
* CMake configuration files for:
    * Building the project.
    * Downloading and building GoogleTest from sources.
    * Usage of CTest.
    * Generating documentation using Doxygen.

### What This Template Does Not Provide

* Installation configuration (e.g. **CMake INSTALL** target is not configured).
* Support for third-party libraries (e.g. no use of **Conan** or **CMake ExternalProject** etc. - 
not even an `extern/` directory :( - how you use third-party libraries is up to you !)
* Continuous integration etc. ...

### What This Template Might Provide in the Future

* Right now I'm looking into Conan.io, who knows ;)

## Building

Please note that atleast **CMake version 3.12** is required to build this project!

Building has been tested on **Visual Studio 2017 (Windows 10 Professional)** and **g++ 7.3.0 (Ubuntu 18.04.1)**.

### Building the project

Same steps as in every cmake based project ;).

To build the project (executable and libraries) do the following:

1) In the root directory of this project, type these lines to configure the project using cmake.

        mkdir build
        cd build
        cmake ..

    Optionally you can pass more arguments to the call to `cmake` in the last line, like specifiying which generator to use, etc.

2) Now to build the project, type (while still being in directory `scratch/build/`):

        cmake --build .

CMake is configured to place the output binaires in `bin/`.

### Build the documentation

Note that doxygen documentation is not generated by default. If you want it to be built then type:

    cmake --build . --target doc_doxygen

This will generate HTML documentation in directory `scratch/doc/doxygen/html/`. Simply open file `index.html` in this directory with your browser.

#### Running the tests

To run the tests, in directory `build/` type:

    ctest .

## Documentation

Further documentation can be found in the following files in `doc/`:

*   Description of the [project structure (doc/STRUCTURE.md)](doc/STRUCTURE.md) 

## Keep a Changelog !

If you haven't read [this guide](https://keepachangelog.com/en/1.0.0/) you should do it.
I recommend keeping a changelog also for your small and personal projects. 

Of course this template also has a changelog (a pretty empty one though): [Changelog](CHANGELOG.md)

## Version numbers found in this template

A quick note about the meaningfulness of the version numbers found in this project (hint: there is mostly no meaning):

* The version numbers of the project's componenents are not really reflecting any real revision and 
are purely fictional to illustrate the fact that (stating the obvious here:) a project can of course consist of multiple components with varying versions.
* Only the version found in [CHANGELOG.md](CHANGELOG.md) as well as in CMakeLists.txt at this 
project's root directory really reflect the current version of this template as a whole.