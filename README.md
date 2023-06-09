Shader: https://github.com/festivize/PrimoToon
Assets: https://github.com/zeroruka/GI-Assets

Texture and texture channel usage

Base Diffuse = Base texture.
Base Alpha = Used as a bloom/emissive mask in the body, alpha depending on texture, or as a blush mask for the face
Shadow Ramp = Determines shadow and lit color, as well as fake SSS. To be used with half lambert shading but you can still use it with ordinary lambert, just multiply SSS Rate by 2
Lightmap R = Used in calculating non-metallic specular AND Metallic matcap mask (< 0.9)
Lightmap G = Permanent Shadows/Occlusion (< 0.2), and > 0.8 separates eye from the hair (only applies to hair lightmap, sometimes body lightmap like Yae’s)
Lightmap B = Used in calculating both non-metallic and metallic specular (as a whole)
Lightmap A = Used as a threshold for outline colors, multiple specular values and the ramp textures, divided into max of 5 regions
Normal Map - enough said
Specular Ramp - shadow ramp but specular 
Vertex Color R = Used to complement Lightmap G
Vertex Color G = Used for vertex ramp width, I also personally use this channel for outlines depending on camera distance
Vertex Color B = Used for outlines (idk how exactly), personally I use this for Z-offset
Vertex Color A = Base outline thickness that does not scale with camera
Metal MatCap texture = Used as a matcap on the metallic matcap mask (Lightmap R)
Face Shadow Mask texture (alpha included) = controls lighting for the mouth and eyebrows
Face Lightmap texture = controls face lighting
