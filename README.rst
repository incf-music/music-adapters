music-adapters
==============

A collection of adapters for the MUSIC library (https://github.com/INCF/MUSIC).

Run 'doxygen' to create the documentation including example configurations.

Installing requirements with conda
==================================
.. code:: bash

  conda install pkg-config jsoncpp blas gsl
  conda install -c conda-forge cppzmq

Installing requirements with apt
================================
.. code:: bash

  sudo apt install pkg-config libjsoncpp-dev libzmq3-dev libblas-dev libgsl-dev

Compiling and making
====================
.. code:: bash

  cmake -DCMAKE_INSTALL_PREFIX:PATH=<PREFIX> -DMUSIC_ROOT_DIR=<MUSIC_INSTALL_PREFIX> <music-adapters_SOURCE>
  make
  make install

If the compiler runs into trouble because it can't find a file "json.h", try

.. code:: bash

  # if libjsoncpp was installed with apt
  cp -r /usr/include/jsoncpp/json <music-adapters_SOURCE>/base
  # if libjsoncpp was installed with anaconda
  cp -r ~/anaconda2/pkgs/jsoncpp-<SUFFIX>/include/jsoncpp/json <music-adapters_SOURCE>/base
 
or copying any other folder "json" containing a file "json.h" to the source directory.

Sometimes, cmake does not find mpi.h because it selects the wrong compilers. In this case try:

.. code:: bash

  cmake -DCMAKE_INSTALL_PREFIX:PATH=<PREFIX> -DMUSIC_ROOT_DIR=<MUSIC_INSTALL_PREFIX> -DCMAKE_C_COMPILER=mpicc -DCMAKE_CXX_COMPILER=mpic++ <music-adapters_SOURCE>

