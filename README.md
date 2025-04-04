# TritonRoute-WXL
**TritonRoute-WXL**, which is built on the open source detailed router 
TritonRoute, 
is an open source router for modern industrial designs. 
The router consists of several main building blocks, including 
pin access analysis, global routing, track assignment, detailed routing, 
and a DRC engine. 
TritonRoute-WXL was developed by graduate students Lutong Wang and Bangqi Xu at 
UC San Diego in La Jolla, California.

TritonRoute-WXL provides industry standard LEF/DEF interface with 
support of [ISPD-2018](http://www.ispd.cc/contests/18/) and 
[ISPD-2019](http://www.ispd.cc/contests/19/) contest-compatible route guide 
format. In addition, it provides a global-detailed routing interface
that is compatibale with existing contest-based interface.

## This version ##

This version of TritonRoute makes minor modifications to work with
the ACT tools for asynchronous design. Apart from minor fixes to warnings,
the main differences are (i) changed the default options used by the
detailed router, and (ii) the LEF/DEF libraries are assumed to be installed
in ACT_HOME, so they have been removed from the build process.

## Installation ##

TritonRoute-WXL is tested in 64-bit CentOS 6/7 environments with the following
prerequisites:
* A compatible C++ compiler supporting C++17 (GCC 7 and above)
* Boost >= 1.68.0
* OpenMP >= 4.5
* Bison >= 3.0.4
* zlib >= 1.2.7
* CMake >= 3.1
* LEF/DEF libraries from Si2 installed in $ACT_HOME

To install this version of TritonRoute-WXL, make sure that the environment variable ACT_HOME
is set to the install directory for the ACT tools. Also, make sure that the LEF/DEF libraries
are also installed there. After this:
```
$ git clone https://github.com/asyncvlsi/TritonRoute-WXL.git
$ cd TritonRoute 
$ mkdir build
$ cd build
$ cmake -DCMAKE_INSTALL_PREFIX=$ACT_HOME ../
$ make
$ make install
```
   
To run TritonRoute-WXL for detailed routing: 
```
$ ./TritonRoute -lef <LEF_FILE> -def <DEF_FILE> -guide <GUIDE_FILE> -output <OUTPUT_DEF>
```

To run TritonRoute-WXL for global-detailed routing: 
```
$ ./TritonRoute -lef <LEF_FILE> -def <DEF_FILE> -output <OUTPUT_DEF>
```

## Supported Technologies ##
* ISPD-2018 and ISPD-2019 Initial Detailed Routing Contests 

## References ##
Please cite the following paper(s) for publication:
* A. B. Kahng, L. Wang and B. Xu, "TritonRoute: The Open Source Detailed Router", IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems (2020), doi:10.1109/TCAD.2020.3003234.
* A. B. Kahng, L. Wang and B. Xu, "The Tao of PAO: Anatomy of a Pin Access Oracle for Detailed Routing", Proc. ACM/IEEE Design Automation Conf., 2020, pp. 1-6.

## License ##
* [BSD 3-clause License](LICENSE) 


