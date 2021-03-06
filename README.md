# Ray tracing  
This is pure C++ CPU ray tracing, with no additional libraries, only standart  
It uses .ppm image format (you can google image viewers for your OS)  

## Make  
There is a makefile, so `make` should do it  
No additional libs required. No OpenGl, no windows/linux os libraries, no image libraries  
Only C++ with C++11 (may be C++14?) support

## Usage  
There is a main class called `RayTracer`. It has several main options  
* `objects` array: it's a vector of 3d objects, that must extend `GeometryPrimitive` interface. There are some prebuilt objects like `Sphere` or `Mesh`  
* `lights` array: just a vector of light positions in space. For now, light is only a point beaming in every direction  
* `camera` object: a struct with some properties of a camera in space. This is a 'viewer' position, direction and FOV properties. Also it defines resulting image resolution  
* `antialiasing`: how many rays to send in 1 pixel. WARNING: real ray number will be squared, so if AA=2, there will be 4 rays in pixel  
See `main.cpp` with two example scenes  

## Info  
It usign Phong lighting method, but I'm not sure, that I've implemented it correctly  
Also, for now there is no refraction nor transparency  
This was tested with teapot model  

## Motivation  
The main idea is that this must use no libraries outside standart, and be os independent  
That's why it calculating on CPU (because you need OpenGL for GPU), using .ppm images, which is basic bitmap with near no header: it's easy to implement with no libs. I use binary file format to save at least some of the disk space 

## Examples
![scene1](https://github.com/Masafi/raytracing/raw/master/examples/scene1.jpg)
![scene2](https://github.com/Masafi/raytracing/raw/master/examples/scene2.jpg)
