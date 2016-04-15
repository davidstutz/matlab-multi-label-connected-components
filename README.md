# Multi-Label Connected Components in MatLab

This repository contains a MEX wrapper for [Ali Rahimi](http://xenia.media.mit.edu/~rahimi/connected/) C++ implementation of fast, multi-label connected components.

## Building

Open MatLab (tested with 2015b on Ubuntu 14.04):

	>> mex sp_fast_connected_relabel.cpp
	Building with 'g++'.
	Warning: You are using gcc version '4.8.4'. The version of gcc is not supported. The version currently supported with MEX is
	'4.7.x'. For a list of currently supported compilers see: http://www.mathworks.com/support/compilers/current_release. 
	 
	Warning: You are using gcc version '4.8.4-2ubuntu1~14.04.1)'. The version of gcc is not supported. The version currently
	supported with MEX is '4.7.x'. For a list of currently supported compilers see:
	http://www.mathworks.com/support/compilers/current_release. 
	 
	MEX completed successfully.

## Usage

For simplicity, the function operates on matrices of type double (i.e. `mxDOUBLE_CLASS`), therefore, the image has to be converted to double:

	>> image = imread('checkerboard.png');
	>> labels = sp_fast_connected_relabel(double(image));
	>> imshow(uint8(labels)*10)
	>> imwrite(uint8(labels)*10, 'checkerboard_components.png');

The output can be seen below:

![Example: checkerboard and connected components of checkerboard.](screenshot.png?raw=true "Example: checkerboard and connected components of checkerboard")

## License

The copyright holder of `connected_components.h` is [Ali Rahimi's](http://xenia.media.mit.edu/~rahimi/connected/). The MEX wrapper is published under the BSD 3-Clause license:

Copyright (c) 2016, David Stutz
All rights reserved.

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
* Neither the name of the copyright holder nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
