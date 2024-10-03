The Process of applying a material to an object 

![[Pasted image 20241002150734.png]]

To perform Shading you do the following 
- Computer light reflected toward camera at a specific shading point
![[Pasted image 20241002151208.png]]

**Shading will not create shadows in the environment**

## Diffuse Reflection 

Light is scattered uniformly in all directions 
![[Pasted image 20241002151331.png]]\

But how much light is received? 

![[Pasted image 20241002151410.png]]

### Light Falloff 

![[Pasted image 20241002151447.png]]

## Models 

### [[Blinn-Phong Reflectance Model]]

or simple shading model uses the view direction to determine brightness

## Shading Frequency 

![[Pasted image 20241002153335.png]]

![[Pasted image 20241002153854.png]]

### Flat Shading 
shading each triangle 

![[Pasted image 20241002153436.png]]

### Gouraud Shading 

shading each vertex

- Interpolate colors from vertices across the triangle 
- Each vertex has a normal vector
![[Pasted image 20241002153637.png]]

### Phong Shading 

Shading each pixel 
- Interpolate normal vectors across each triangle 
- Compute full shading model at each pixel
![[Pasted image 20241002153830.png]]

*Not related to Blinn-Phong Reflectance Model*

### Per-Vertex Normal Vectors 
[[Vectors]]
![[Pasted image 20241002154343.png]]


### Per-Pixel Normal Vectors 
[[Vectors]]  [[Barycentric Coordinates]]

![[Pasted image 20241002154356.png]]