# BuildCUnitWithCMake
A CMake buildscript to build CUnit

Build steps for Windows with MinGW64:
1) Copy CMakeLists.txt into the CUnit root directory e.g. CUnit-2.1-3
2) cd <path to CUnit root directory>
3) mkdir build
4) cd build
5) cmake [-G "MinGW Makefiles"] -DCMAKE_INSTALL_PREFIX=<path to final lib> ..
6) mingw32-make
7) mingw32-make install


