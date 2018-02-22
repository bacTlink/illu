# Compile

Firstly, clone this repo.
```
git clone --recursive https://github.com/bacTlink/illu.git
```

Copy ```lib64``` and ```include``` from [OptiX 5.0](https://developer.nvidia.com/designworks/optix/download).
```
cp -r /home/linzehui/NVIDIA-OptiX-SDK-5.0.0-linux64/include illu/optix/
cp -r /home/linzehui/NVIDIA-OptiX-SDK-5.0.0-linux64/lib64 illu/optix/
```

Create build directory and enter it.
```
cd illu
mkdir build
cd build
```

Start compilations.
```
cmake ..
make -j4
```

You can run PPM to check the compilations.
```
./bin/optixProgressivePhotonMap -n
```

# PPM
The primitive PPM project is ```optix/advance_SDK/optixProgressivePhotonMap```.
A modified version is ```optix/advance_SDK/primePPM```, which is used to generate training data.

primePPM Change log:

# OptiX
You can edit ```CMakeLists.txt``` to switch from ```optix/advance_SDK``` to ```optix/SDK```.

But please note that you should ```make clean``` before compiling, or you fail.
And you should not compile both of them, or you fail.

PPM is under ```optix/advance_SDK```.

# Caffe
You can ```#include "caffe/caffe.hpp"``` in optix.
Refer to [optixHello](https://github.com/bacTlink/optix_illu/blob/c98ceb4d6a1c77a0c4457d3ad823713c3f41e16e/SDK/optixHello/optixHello.cpp) as an example.
