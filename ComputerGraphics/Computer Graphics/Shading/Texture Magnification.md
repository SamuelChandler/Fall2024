[[Applying Textures]]  [[Texture Mapping]] 

perform if the texture is different from the base object

![[Pasted image 20241002161638.png]]

## Bilinear Interpolation 

done when the texture is too small for the object 

![[Pasted image 20241002161821.png]]

1. Take the 4 nearest sample location, with texture values as labeled 
2. Add the fractional offsets, (s,t) as shown 
![[Pasted image 20241002161928.png]]

3. MATH
![[Pasted image 20241002162155.png]]

