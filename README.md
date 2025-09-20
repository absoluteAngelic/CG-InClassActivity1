# CG-InClassActivity1

All screenshots are in the [Screenshots](https://github.com/absoluteAngelic/CG-InClassActivity1/Screenshots) folder

I made a multiuv shader that can apply multiple uvs onto an object, updated it so that it responds to the camera angle and position, made a shader that can reflect from a cubemap, a shader that reacts to the object moving through space, and a shader that uses all available properties of the shader to alter its appearance.

When the range went to 0, the model was flat and tinted dark green. When the range went to 5, it became very bright and the texture was fully saturated.

When all rgb values on the material are 0, it looked exactly as it did with the range at 0; the model appeared flat and tinted dark green

`float3 R = reflect(-V,N);` creates a vector R that is reflected off of the model from the camera
`half3 env = SAMPLE_TEXTURECUBE(_myCube,sampler_myCube,R).rgb;` creates a variable env that stores rgb data using the vector R (stores colour data from the reflection using the cubemap in the material) and then this variable is used to apply the float and vector properties to the lighting. When the cubemap on the material is the same as the one used in the actual sky, it creates the illusion that the object is truly reflecting the skybox around it.

At the start of the activity, I accidentally created a project in unity 2022 which gave errors from the shaders and wouldn't work at all. With a suggestion from the teacher, I made a new project in unity 6 and it worked perfectly. Copying code from the slides wasn't too hard for me as I can type quickly, and I also helped a friend debug his code for the first shader. Understanding the code itself and what the shaders were doing was hard for me, and I will dedicate more time to learning the fundamentals of the shader code. For future assignments, I will ensure that I create the project with unity 6 to avoid errors. While working on this assignment/activity, I learned that you can have a reflection shader that uses a cubemap for the reflections instead of the skybox, and I remember playing certain games when I was younger with certain objects that were reflecting things that weren't visible anywhere else in the game world, and now I understand how they achieved that effect. It's very cool to see the technical parts behind all the game visuals I've been seeing my whole life.
