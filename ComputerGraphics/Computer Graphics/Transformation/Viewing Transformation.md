[[3D Transformations]]  [[Composing Transforms]] 

![[Pasted image 20241001212042.png]]

## View/Camera Transformation

To Start we need to determine the camera we are using 
- position 
- gaze Direction 
- Up Direction 

![[Pasted image 20241001212146.png]]

when the camera and objects move together, the resulting photo will be the same

![[Pasted image 20241001212322.png]]

We Transform the camera by $M_{view}$ 

![[Pasted image 20241001212640.png]]

### The Math :( 

![[Pasted image 20241001212710.png]]


## Projection Transformation

The Idea of Converting 3D to 2D 

![[Pasted image 20241001213113.png]]


### Orthographic Projection 

![[Pasted image 20241001213404.png]]

![[Pasted image 20241001213435.png]]

Steps: 
1. Center cuboid by [[3D Transformations]] 
2. Scale into canonical cube

#### Transformation Matrix 
![[Pasted image 20241001213621.png]]

Depth does not matter for the orthographic Projection 

### Perspective Projection 

[[Homogeneous Coordinates]]

![[Pasted image 20241001214504.png]]

Steps: 
1. Squish the frustum into the cuboid (n-> n, f ->f) ($M_{persp -> othro}$) 
2. Do orthographic projection 
![[Pasted image 20241001215116.png]]

#### Transformation 

To find the relationship between transformed points (x',y',z') and the original points (x,y,z)

![[Pasted image 20241001215326.png]]

##### Sourcing $M_{persp -> othro}$ 

![[Pasted image 20241001215503.png]]

![[Pasted image 20241001220439.png]]
![[Pasted image 20241001220522.png]]

![[Pasted image 20241001220533.png]]

![[Pasted image 20241001220544.png]]


#### Getting l,r,b,t

![[Pasted image 20241001221254.png]]

![[Pasted image 20241001221311.png]]

#### Perspective Matrix 

![[Pasted image 20241002145944.png]]
