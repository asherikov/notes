List of defined macros (GCC, Clang)
===================================
    clang -dM -E -x c /dev/null



List symbols in a shared library
================================
    objdump -TC <lib>


Print array in lldb
===================
    *(double(*)[18]) A.m_storage.m_data


Searching functions in lldb
===========================
    image lookup -r -n <FUNC_REGEX>


Debug
=====
    rr-project.org
