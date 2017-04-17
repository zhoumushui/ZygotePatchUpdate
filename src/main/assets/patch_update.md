## Patch Update Note

Copyright © 2017 www.zhoumushui.com


###1.下载Binary Diff:
 
>下载地址:<br>Http://www.daemonology.net/bsdiff/
 <br>V4.3:Http://www.daemonology.net/bsdiff/bsdiff-4.3.tar.gz
 
 解压后文件：
>- bsdiff.1
>- bsdiff.c
>- bspatch.1
>- bspatch.c
>- MakeFile


### 2.编译bsdiff
在Ubuntu中切到bsdiff目录，执行make编译，报错：
> Makefile:13: *** missing separator.  Stop.

修改MakeFile，将install下面的if,endif添加一个缩进，然后继续编译，报错：
> cc -O3 -lbz2    bsdiff.c   -o bsdiff
  bsdiff.c:33: fatal error: bzlib.h: No such file or directory
  compilation terminated.
  make: *** [bsdiff] Error 1
  
安装libbz2：
> sudo apt-get install libbz2-dev

安装成功后再次make，编译成功，生成bsdiff和bspatch：
> cc -O3 -lbz2    bsdiff.c   -o bsdiff<br>
cc -O3 -lbz2    bspatch.c   -o bspatch

  
  



 
