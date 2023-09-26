# HairNet_orient2D
Generate 2D Orientation Maps for [HairNet: Single-View Hair Reconstruction using Convolutional Neural Networks](https://arxiv.org/abs/1806.07467).
This project is a fork of [https://github.com/papagina/HairNet_orient2D].

# Installation
## Ubuntu 22.04
```
# cd to project root
sudo apt install libopencv-dev libfftw3-dev
mkdir build
cmake -S Hair_Orient2D/ -B build
cd build
make
```
If cmake fails to locate fftw3, try looking for its installation path via `dpkg -L libfftw3-dev` and update `Hair_Orient2D/CMakeLists.txt` accordingly.

# Running
Make a base directory, containing following subdirectories:
- `img`: RGB images containing face and hair
- `seg`: Segmentation maps of hair
- `body_img`: optional; only needed if want to visualise body with orientation map.

Each RGB image inside `img` must have a corresponding image with the same name and dimensions inside `seg` (and optionally inside `body_image` as well).
All images must be square (512x512 or 800x800 recommended).
Have all images be PNG format, and for `seg` and `body_img` have foreground be white and background black.
See `test_imgs/` as an example.

Run via:
```
# cd to project root
./build/Orient2D path/to/base/dir
```
