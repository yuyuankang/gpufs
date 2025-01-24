gpufs
=====

GPUfs - File system support for NVIDIA GPUs

This is a GPUfs 0.1 distribution

## how to compile and run 

``` shell
cd libgpufs
make install
```

This will create 2 folders in the root directory: `lib` and `include`. The `lib` folder contains the `libgpufs.a` file and the `include` folder contains the header files.

Also, I made some modification to make sure the compiling is fit for Nvidia A100 GPU:
In any Makefile, replace code=sm_<any number>,arch=compute_<any number> with code=sm_80,arch=compute_80

## run the examples
