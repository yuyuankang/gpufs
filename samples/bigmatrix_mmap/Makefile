# # Makefile for GPUfs and related projects

# # Common flags and directories
# CUDA_DIR=/usr/local/cuda
# LIBCUDA=-L$(CUDA_DIR)/lib64 -lcudart -lcudadevrt
# CUDAINC=-I$(CUDA_DIR)/include
# CXXFLAGS=-fopenmp -g -O2
# CUFLAGS=--std=c++11 -O3 -rdc=true -maxrregcount=32 -gencode arch=compute_80,code=sm_80
# LINKFLAGS=-O3 -rdc=true -gencode arch=compute_80,code=sm_80
# NVCC=$(CUDA_DIR)/bin/nvcc $(CUDAINC)

# # GPUFS specific paths and libraries
# LIBGPUFSDIR=../../lib/
# GPUFSINC=../../include
# GPUFSLIBS=-lgpufs -L$(LIBGPUFSDIR)

# # Targets
# PAYLOAD=bigmatrix_mmap.cu
# MAIN=fs
# OBJS=fs.o

# # Rules
# all: $(MAIN) bigmatrix_cpu bigmatrix_nofs bigmatrix_nofs_naive

# $(MAIN): $(OBJS)
# 	$(NVCC) $(LINKFLAGS) -o $(MAIN) $(OBJS) $(GPUFSLIBS) $(LIBCUDA)

# fs.o: fs.cu
# 	$(NVCC) $(CUFLAGS) -I$(GPUFSINC) -c $<

# bigmatrix_cpu.o: bigmatrix_cpu.cpp
# 	$(CXX) -o bigmatrix_cpu.o -c bigmatrix_cpu.cpp $(CXXFLAGS)

# bigmatrix_cpu: bigmatrix_cpu.o
# 	$(CXX) -o bigmatrix_cpu bigmatrix_cpu.o $(CXXFLAGS)

# bigmatrix_nofs: bigmatrix_nofs.cu
# 	$(NVCC) -o bigmatrix_nofs bigmatrix_nofs.cu -I$(LIBGPUFSDIR)

# bigmatrix_nofs_naive: bigmatrix_nofs_naive.cu
# 	$(NVCC) -o bigmatrix_nofs_naive bigmatrix_nofs_naive.cu -I$(LIBGPUFSDIR)

# clean:
# 	rm -f $(MAIN) bigmatrix_cpu bigmatrix_nofs bigmatrix_nofs_naive *.o *~


# Makefile for GPUfs and related projects

# Common flags and directories
CUDA_DIR=/usr/local/cuda
LIBCUDA=-L$(CUDA_DIR)/lib64 -lcudart -lcudadevrt
CUDAINC=-I$(CUDA_DIR)/include
CXXFLAGS=-fopenmp -g -O2
CUFLAGS=--std=c++11 -O3 -rdc=true -maxrregcount=32 -gencode arch=compute_80,code=sm_80
LINKFLAGS=-O3 -rdc=true -gencode arch=compute_80,code=sm_80
NVCC=$(CUDA_DIR)/bin/nvcc $(CUDAINC)

# GPUFS specific paths and libraries
LIBGPUFSDIR=../../lib
GPUFSINC=../../include
GPUFSLIBS=-lgpufs -L$(LIBGPUFSDIR)

# Targets
PAYLOAD=bigmatrix_mmap.cu
MAIN=fs
OBJS=fs.o

# Rules
all: $(MAIN) bigmatrix_cpu bigmatrix_nofs bigmatrix_nofs_naive

$(MAIN): $(OBJS)
	$(NVCC) $(LINKFLAGS) -o $(MAIN) $(OBJS) $(GPUFSLIBS) $(LIBCUDA)

fs.o: fs.cu
	$(NVCC) $(CUFLAGS) -I$(GPUFSINC) -c $<

bigmatrix_cpu.o: bigmatrix_cpu.cpp
	$(CXX) -o bigmatrix_cpu.o -c bigmatrix_cpu.cpp $(CXXFLAGS)

bigmatrix_cpu: bigmatrix_cpu.o
	$(CXX) -o bigmatrix_cpu bigmatrix_cpu.o $(CXXFLAGS)

bigmatrix_nofs: bigmatrix_nofs.cu
	$(NVCC) $(CUFLAGS) -I$(GPUFSINC) -o bigmatrix_nofs bigmatrix_nofs.cu

bigmatrix_nofs_naive: bigmatrix_nofs_naive.cu
	$(NVCC) $(CUFLAGS) -I$(GPUFSINC) -o bigmatrix_nofs_naive bigmatrix_nofs_naive.cu

clean:
	rm -f $(MAIN) bigmatrix_cpu bigmatrix_nofs bigmatrix_nofs_naive *.o *~