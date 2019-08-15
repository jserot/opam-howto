This repository contains some example code showing how to define and use
a simple [opam](http://opam.ocaml.org) package.

Two versions are provided : with and without using the [dune](https://github.com/ocaml/dune) build
system.

Each version consists in two directories:
* a directory named `build`, for building and installing the package
* a directory named `use`, for building and running a small program using the package.

The package itself, named `dummy` consists in a single module, `hello`.

Installation
------------

  * `git clone https://github.com/jserot/opam-howto`
  * `cd opam-howto`

Usage
-----

To build the package:

* `cd` to the corresponding directory (`with-dune` or `without-dune`)
* `cd build`
* `make` 
* `make install`
* `opam install .`

To test it:

* `cd ../use` 
* `make`

The latest command should compile a program named `main` (both byte and native code) and launch it,
displaying `Hello, world !`).

The generated `html` documentation of the package (not very informative here !) can be viewed by
invoking `make viewdoc` either from the `build` or `use` directory.

Pre-requisites
--------------

* An [Ocaml](http://ocaml.org/docs/install.html) compiler, version >= 4.06.0 with the following packages

* The [ocamlfind](https://opam.ocaml.org/packages/ocamlfind) package is required for building the
  test program in the `without-dune` version

* The `with-dune` version of course requires the [dune](https://opam.ocaml.org/packages/dune)
  package (the provided code has been tested with version >= 1.11).

