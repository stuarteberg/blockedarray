blockedarray
============

C++ code and boost::python wrapper for a blocked,
in-memory compressed array that supports read/write
access to arbitrary regions of interest.

The main class is `BlockedArray`. It stores data in
blocks (of a size to be specified in the constructor).
Each block is stored compressed in memory, using
google snappy, a fast compression/decompression algorithm.

Regions of interest of arbitrary offset and shape can be
read, written and deleted.

This class is useful if the whole dataset does not fit
into memory. It is the intention that this class is evaluated
as a replacement for
[lazyflow](http://github.com/ilastik/lazyflow)'s
`OpBlockedArrayCache`, `OpSlicedBlockArrayCache`,
`OpCompressedCache`.
Towards this goal, a preliminary operator wrapper can be found
in `blockedarray/lazyflow`.

installation
------------

```bash
export PYTHONPATH=$PWD:$PYTHONPATH
mkdir build
cd build
cmake ..
git submodule update
make
```
