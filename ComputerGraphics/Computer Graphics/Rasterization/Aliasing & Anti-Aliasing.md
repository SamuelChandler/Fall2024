[[Rasterization]] 
## Aliasing 

When the Sampling Frequency is at to low of a frequency and is not capturing all of the information needed

Signals are changing too fast, but sampling is too slow 

Examples: 
- Jaggies - sampling in space 
- Moire - under sampling images 
- Wagon wheel effect - sampling in time

Why? 
[[Frequency Domain]] 

### Reducing Aliasing error

#### Increase Sampling Rate
- Increasing the distance between replicas in the Fourier domain 
- higher resolution displays, sensors, framebuffers 
- usually is very costly 
#### Anti Aliasing 
- making the fourier contents 'narrower' before repeating 
- filtering out high freq. before sampling 
![[Pasted image 20241002133532.png]]


## Anti-Aliasing 

A technique to counter aliasing through techniques that smooth the edges of an object to make it more realistic

### Examples: 
[[Blurring]]   [[Sampling#Super Sampling]]

