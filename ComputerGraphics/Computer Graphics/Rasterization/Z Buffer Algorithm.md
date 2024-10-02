improvement from the [[Painters Algorithm]]

used in [[Rasterization]] to determine depth of the read in object
## Idea: 
- store the current min z-value for each sample (pixel)
- Needs an additional buffer for depth values 
	-  frame buffer stores color values 
	- depth buffer stores the depth of the reading 

![[Pasted image 20241002134328.png]]

## Implementation 

![[Pasted image 20241002134338.png]]

## Complexity 

![[Pasted image 20241002134448.png]]