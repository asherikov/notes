Long output format, disable more and crash dumps
================================================
    format long;
    more off;
    crash_dumps_octave_core(0);



Set compiler and linker for C++ code
====================================
Version: Octave 3.8.1, FreeBSD 10.0

Octave is compiled with gcc 4.7 on FreeBSD, while default compiler is clang.
When a MEX module is compiled using Octave, the default compiler is used, and
the compiled module does not work. This problem can be avoided by forcing
Octave to use gcc as compiler and linker:

    setenv ('CXX', 'g++47')
    setenv ('DL_LD', 'g++47')



FLTK and printing offscreen images
==================================
Version: Octave 3.8.1

Setting: A script which redraws and prints a figure iteratively.

Problem: If the X-windows screen where the script is running is not active,
printing does not work.

Should be fixed in the new versions:
http://octave.1599824.n4.nabble.com/Offscreen-rendering-with-OSMesa-and-gl2ps-td4667963.html



Printing figures with overlayed axes
====================================
Version: Octave 3.8.1

Setting: Two overlappping axes are created on the same figure
    ax1 = axes('Position', [0.05 0.05 0.9 0.9]);
    ax2 = axes('Position', [0.65 0.60 0.3 0.35]);
The first is with 3D plot the second -- with 2D plot. The second one is
intended to be cover a part of the first one. 

Problem: The figure is displayed as intended, but the printed version is
mangled. The first axis is partially drawn on the top of the second one.

Workaround: Draw and print each axis separately, then overlay eps files as
described in 'postscript_pdf.txt'.


Compatibility with MATLAB
=========================
                                MATLAB          Octave
---------------------------------------------------------------------
Empty cell                      {}              cell(), {}

or(1)                           fails           works

some_array{end+1} = 1           not supported   supported

Default values for function     not supported   supported
parameters

Splitting a string with
    strsplit('str', '_')        not supported   supported
    regexp('str','_','split')   supported       supported

Broadcasting when using         not supported   supported
cellfun()
---------------------------------------------------------------------
