Startup file
============

    rmaxima  --init-mac='~/.maxima_startup' --init-lisp='~/.maxima_startup.lisp'



Commands
========

    addcol
    addrow
    diag -- construct block diagonal matrix

    zeromatrix(2,5)
    zerofor(M)

    display2d : false
    tex()



Simplification using hyperbolic functions
=========================================
This function must be added to the startup file

    hypsimp(x,M):= ratsimp(subst(x/%i,x,demoivre(subst(x*%i,x,M))));

Usage:
------------------------------------------------------------------------------
(%i7) expr: (%e^(a*b) - %e^-(a*b))/2;
                                  a b     - a b
                                %e    - %e
(%o7)                           ---------------
                                       2
(%i8) hypsimp(a*b, expr);
(%o8)                              sinh(a b)
------------------------------------------------------------------------------



Discretization of a system
==========================
    load("diag");
    Ad: mat_function(exp, A*T);
    Bd: expand(integrate(mat_function(exp, A*t), t, 0, T).B);



Matrix exponential
==================
    load("diag");
    A : matrix([2,1],[0,2]);
    mat_function(exp, A);



Cross product
=============
    load("vect");
    express([1,2,3]~[4,5,6]);



Jacobian
========
    f1: x + y;
    f2: sin(y);
    f3: x + z;
    J: jacobian ([f1, f2, f3], [x, y, z]);

