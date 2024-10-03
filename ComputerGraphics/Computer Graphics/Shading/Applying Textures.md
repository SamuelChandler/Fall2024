[[Rasterization]] [[Texture Mapping]]

For each rasterized screen sample (x,y):

1. (u,v) = evaluate texture coordinate at (x,y) using [[Barycentric Coordinates]]
2. texcolor = texture.sample(u,v)
3. set sample's color to tex color, or set $k_d$ as seen in the [[Blinn-Phong Reflectance Model]]

