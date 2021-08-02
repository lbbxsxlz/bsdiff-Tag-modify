# bsdiff-tag-modify
bsdiff-releases-tar.gz  modify

## origin releases tag
[tag](https://github.com/mendsley/bsdiff/releases)

[bsdiff-4.3-endsley.tar.gz](https://github.com/mendsley/bsdiff/archive/refs/tags/v4.3-endsley.tar.gz)

[bsdiff-4.3.tar.gz](https://github.com/mendsley/bsdiff/archive/refs/tags/v4.3.tar.gz)

## License
Copyright 2003-2005 Colin Percival<br>
Copyright 2012 Matthew Endsley

This project is governed by the BSD 2-clause license.<br>
For details see the file titled LICENSE in the project root folder.


## how to use
bsdiff oldfile newfile patchfile

bspatch oldfile newfile patchfile

## bzip2 compile
tar zxvf bzip2-1.0.8.tar.gz;
cd bzip2-1.0.8;
patch -p0 < Makefile.patch;

make clean;make CROSS=aarch64-himix210-linux-sd3403v100-v1-

