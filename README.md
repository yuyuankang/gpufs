gpufs
=====

GPUfs - File system support for NVIDIA GPUs

This is a GPUfs 0.1 distribution

## how to compile and run 

``` shell
cd libgpufs
mkdir release
make OUTPUTDIR=release
```

Then you will find the following files in the release folder:
```
.
├── async_ipc.o
├── cpu_ipc.o
├── fs_calls.o
├── fs_debug.o
├── fs_initializer.o
├── fs_structures.o
├── generic_ringbuf.o
├── gpufs_con_lib.o
├── hashMap.o
├── libgpufs.a
├── mallocfree.o
└── timer.o
```