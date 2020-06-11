music-adapters
==============

A collection of adapters for the MUSIC library (https://github.com/INCF/MUSIC).

Run 'doxygen' to create the documentation including example configurations.

Installation
============
Requirements with conda:

.. code:: bash
  conda install pkg-config jsoncpp blas gsl
  conda install -c conda-forge cppzmq
  mkdir <music-adapters_SOURCE>/base/jsoncpp
  cp -r ~/anaconda2/pkgs/jsoncpp-<SUFFIX>/include/json <music-adapters_SOURCE>/base/jsoncpp

Requirements with apt:

.. code:: bash
  sudo apt install pkg-config libjsoncpp-dev libzmq3-dev libblas-dev libgsl-dev
  cp -r /usr/include/jsoncpp <music-adapters_SOURCE>/base

If the jsoncpp header files are not in these places, search your include directory for a folder json including a file json.h, and put this folder into <music-adapters_SOURCE>/base/jsoncpp.

Compiling and making:

.. code:: bash
  cmake -DCMAKE_INSTALL_PREFIX:PATH=<PREFIX> -DMUSIC_ROOT_DIR=<MUSIC_INSTALL_PREFIX> <music-adapters_SOURCE>
  make
  make install
