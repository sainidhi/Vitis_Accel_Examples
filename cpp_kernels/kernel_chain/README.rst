Stream Chain Matrix Multiplication (C)
======================================

This is a kernel containing the cascaded Matrix Multiplication using dataflow. ap_ctrl_chain is enabled for this kernel to showcase how multiple enqueue of Kernel calls can be overlapped to give higher performance. ap_ctrl_chain allow kernel to start processing of next kernel operation before completing the current kernel operation.

**KEY CONCEPTS:** ap_ctrl_chain, PLRAM

EXCLUDED PLATFORMS
------------------

Platforms containing following strings in their names are not supported for this example :

::

   samsung
   vck
   zc

DESIGN FILES
------------

Application code is located in the src directory. Accelerator binary files will be compiled to the xclbin directory. The xclbin directory is required by the Makefile and its contents will be filled during compilation. A listing of all the files in this example is shown below

::

   src/host.cpp
   src/krnl_chain_mmult.cpp
   src/krnl_mmult.hpp
   src/krnl_simple_mmult.cpp
   
COMMAND LINE ARGUMENTS
----------------------

Once the environment has been configured, the application can be executed by

::

   ./kernel_chain <krnl_mmult XCLBIN>

COMMANDS FOR WINDOWS FLOW
-------------------------

Once the environment has been configured, run the following commands :

::

   cd cmake_build
   cmake -G "Visual Studio 15 2017 Win64" -DCMAKE_BUILD_TYPE=Debug -DXILINX_XRT=<set xilinx xrt path> -DOCL_ROOT=<set ocl root path>
   cmake --build . --verbose --config Debug --target install

   For Example : 
   cd cmake_build
   cmake -G "Visual Studio 15 2017 Win64" -DCMAKE_BUILD_TYPE=Debug -DXILINX_XRT=C:\Xilinx\XRT -DOCL_ROOT=C:\Xilinx\XRT\ext
   cmake --build . --verbose --config Debug --target install
