used in [[Shading]]

uses the view direction to determine brightness

![[Pasted image 20241002152245.png]]

This model Uses a combination of Ambient, Diffusion, and Specular shading to perform lighting 
![[Pasted image 20241002153109.png]]
### Lambertian (Diffuse) Shading 
![[Pasted image 20241002151858.png]]

produces the appearance of diffusion 

![[Pasted image 20241002151951.png]]


## Specular Term

![[Pasted image 20241002152309.png]]

![[Pasted image 20241002152628.png]]
### Cosine Power Plots 

Increasing p narrows the reflection lobe

![[Pasted image 20241002152608.png]]

## Ambient Term 

shading does not depend on anything 
- add constant color to account for disregarded illumination and fill in black shadows 
- Your kinda faking it 
![[Pasted image 20241002152827.png]]