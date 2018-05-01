cmake_minimum_required(VERSION 2.8.8)
project(illu)


add_subdirectory(caffe_illu)

set(USING_CAFFE ON)
# add_subdirectory(optix/SDK)
add_subdirectory(optix/advance_SDK)
