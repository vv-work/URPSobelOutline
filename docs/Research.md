# Outline shader

## Ideas

- MRTK Quest 2 test.
- MRTK has it's post processing outline somehow working in post processing if I can merge those two solutions
- MRTK also has it's scanning shader
- MRTK surface shader on Meta Quest 2

- I need to draw outline and edges.
- Use Furaz solution and claim it's mine

But there is something something with a buffer.

## Log


> 9/15/22 07:33:43 PM


I need to make Outline shader and I have less then 12 hours for that. 

Great just great. I got so much time to do that and somehow I procrastinated till the very last moment to start doing that.

That is simply great. I will never ever do that again.

I JUST NEED TO START DOING 

5 minutes into the work It's simply Plan

Question: How to make it really fast?

- Non Transperent shader with outline
- Research how exactly current solution is working
- Deadlines
- Understand G-Buffer
- Video Course real quick


> 9/15/22 08:58:12 PM

Got distructed by internal thoughts pithole.

There is like 2 crutial articles and course and a lot of extra materials. Once again the Main Goal.

Outline around Transperent object

Question: What do we need to make an outline ?


We take `SobelOutlineCg` shader

There is that line on the top
```ShaderLab
Cull Off ZWrite Off ZTest Always
```
I think understanding of those things is crutial thing to my success

There ar also

```ShaderLab
#pragma vertex VertMain
#pragma fragment FragMain
```

It looks like those might be a keys to understand the shader.

Plan: 

- Review old article ( 30 min)
- done with newer Article (60 min)
- Take notes from other articles


> 9/16/22 12:17:46 AM

Reading through articles need to admit it sort of boring.

Have a little bit sicking for actions


> 9/16/22 12:23:19 AM

I noticed such variable:

`sambpler2D _CameraGBufferTexture2`

And it looks like it could be solution to my problem

remove HMD loader from manifest json

```json
"com.unity.xr.mock-hmd": "1.3.0-preview.1",
```


> 9/16/22 03:41:45 AM

Vertex Shader is working

It looks like the key is invisible vertex shader.

I made invisible outline.
The layer that should 


> 9/16/22 04:12:47 AM

Made fragmented shader
It's quite obvious that I need to change Post processing input to get result that I want

```ShaderLab

    sampler2D _MainTex;
    sampler2D _CameraDepthTexture;
    sampler2D _CameraGBufferTexture2;
    sampler2D _OcclusionDepthMap;
```

VertMain vs FragMain


> 9/16/22 07:21:07 AM

Solve it in quick dirty way.

Ready f		

Soltution: 
```csharp
   _cam.ResetStereoProjectionMatrices();
```

I descovered the issue


> 9/19/22 07:15:09 AM

Last time I make it work to show up the current progress. 
But now I need to move on with that one.


> Back to work with Ivan

Tasks:

- [ ] Maker URP project
- [ ] Outline with URP test
- [ ] Add something on Shader Graph on top of URP
- [ ] Post processing tranpsernt Block.
- [ ] Creat new buffer
- [ ] Make shader that put info into the buffer
