SDK_ROOT=/home/ubuntu/NVIDIA_GPU_Computing_SDK/
CUDA_ROOT=/usr/local/cuda/
APP=hough
SOURCES=$(APP).cu houghKernels.cu

all: $(SOURCES) 
	sudo ${CXX} -c -lpthread options.cpp ppm.cpp -I./
	nvcc $(SOURCES) -o $(APP) options.o ppm.o -O0 -I${SDK_ROOT}/C/common/inc/ -L${CUDA_ROOT} -lcudart -L${SDK_ROOT}/C/lib/
#     
clean:
	rm -f *.o *~ $(APP) hough.ppm houghOut.pgm sobelOut.pgm