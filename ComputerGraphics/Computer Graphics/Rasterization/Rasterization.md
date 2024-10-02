**the process of converting a vector-based image or object into a raster or bitmap format**

## Triangles

often used to represent more complex objects 
- most basic polygon
- used to make up other polygons

Properties: 
- Guaranteed to be planar 
- Well Defined interior 
- Well defined method for interpolation 

## Methods 

### [[Sampling]]

Steps: 
1. Define a Binary Function 
![[Pasted image 20241002124617.png]]
2. Sample each bit in the given area 
![[Pasted image 20241002124654.png]]

when determining this it is also a good idea to use a bounding box so you are not checking every pixel on the screen 

### How to determine if in the triangle 

[[Vectors]] 

find the three cross products of the triangle and the point if all z values are of the same polarity

## Jaggies 
[[Aliasing & Anti-Aliasing]]

What happens when there is no blur applied and the values are taken discretely

![[Pasted image 20241002125540.png]]

