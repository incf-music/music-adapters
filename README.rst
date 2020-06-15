music-adapters
==============

A collection of adapters for the MUSIC library (https://github.com/INCF/MUSIC).

Run 'doxygen' to create the documentation including example configurations.

Installation
============
.. code:: bash

  sudo apt install pkg-config libjsoncpp-dev libzmq3-dev libblas-dev libgsl-dev
  cmake -DCMAKE_INSTALL_PREFIX:PATH=<PREFIX> -DMUSIC_ROOT_DIR=<MUSIC_INSTALL_PREFIX> <music-adapters_SOURCE>
  make
  make install

sometimes, cmake does not find mpi.h because it selects the wrong compilers. In this case try:

.. code:: bash

  cmake -DCMAKE_INSTALL_PREFIX:PATH=<PREFIX> -DMUSIC_ROOT_DIR=<MUSIC_INSTALL_PREFIX> -DCMAKE_C_COMPILER=mpicc -DCMAKE_CXX_COMPILER=mpic++ <music-adapters_SOURCE>
