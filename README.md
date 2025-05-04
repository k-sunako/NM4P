# 記録

## 2025/05/04

`Cpp` フォルダの`balle.cpp`をコンパイル使用として、以下のコマンドを実行した。

```bash
g++ balle.cpp
```

以下のようなエラーとなった。

```
次のファイルから読み込み:  balle.cpp:3:
NumMeth.h:4:10: 致命的エラー: iostream.h: そのようなファイルやディレクトリはありません
    4 | #include <iostream.h>
      |          ^~~~~~~~~~~~
コンパイルを停止しました。
```

`NumMeth.h` を以下のように修正し、 `balle.cpp` のmain関数の戻り値の型をvoidからintに変更してコンパイル可能となった。

```cpp
// General header file for C++ programs 
// in "Numerical Methods for Physics" 

#include <iostream>
#include <fstream>
#include <assert.h>
#include <math.h>
#include "Matrix.h"

using namespace std;
```


# NM4P
Programs for "Numerical Methods for Physics" by Alejandro Garcia

Python Routines - Tested using Anaconda Jupyter notebook version 4.2.3

Original MATLAB Routines - Tested using MATLAB version 5.2.

Revised MATLAB Routines - Tested using MATLAB version 7.0.1.

C++ Routines - Tested using Microsoft Visual C++ version 5.0.

FORTRAN Routines - Tested using Digital Fortran 77 version 4.0.

These programs are provided for their instructional value.
Although every effort has been made to ensure that they are error
free, neither the author nor the publisher shall be held
responsible or liable for any damage resulting in connection with
or arising from the use of any of these programs.

If you have any questions or comments, please contact:

Alejandro Garcia
Dept. Physics and Astronomy
San Jose State University
San Jose CA 95192
Alejandro.Garcia@sjsu.edu
