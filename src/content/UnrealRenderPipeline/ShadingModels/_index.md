+++
archetype = "chapter"
title = "Shading Models"
weight = 1
+++

{{% badge style="primary" icon="user" title="Author" %}}Alessa Baker{{% /badge %}}
{{% badge style="primary" icon="info-circle" title="Page Status" %}}Complete{{% /badge %}}

## What is a Shading Model?

A shading model simply describes how a given surface renders a pixel depending on lighting, camera direction, and the
surface.

If you are familiar with regularly creating Unlit materials, you are likely trying to do something that doesn't
follow Unreal's PBR (GGX) implementation and trying to remove or add your own lighting to better calculate your material's
aesthetic.  

This unfortunately leads to the limitation of having to use Material Parameter Collections, Dynamic Material
Instances, attempting to implement in a Post Process Material or Mesh Custom Data to pass in the lighting and can get 
quite tedious (and expensive) to implement.

> Side note to Epic, if you can somehow allow for shading models to be implemented via plugins, I will love you forever.  
>   
> A girl can dream. ❤️

## Why create one?

A custom shading model opens up a lot more opportunity when defining the aesthetic you are trying to achieve, specifically,
they allow for masking a given pass and also expose entire lighting (and additional) passes for you to use.

A typical implementation of a custom Shading Model would be Cel Shading, a technique that requires access to the [LightAccumulator]()
in order to be able to have better control over direct shadows attenuation.

{{< figure src="https://ue-cdn.artstation.com/imgproxy/mehlNzVVPPvF1P0QBoR9YS11vuJncCLusjhpYvREunA/filename:CelshadingUE1.png/resizing_type:fit/width:3840/height:2160/aHR0cHM6Ly9kMWl2N2RiNDR5aGd4bi5jbG91ZGZyb250Lm5ldC9pbWFnZXMvOGU1ZTJkMDctYmJmMC00OGE5LWE1MGQtOGIzYTBhYjIyZGY1L2NlbHNoYWRpbmd1ZTEucG5n" title="One3y3 tutorial on Custom Shading Models in UE5 [1]" >}}

Alternatively, if you are just looking to implement a custom Post Process pass (doesn't require engine modification!) then
check out Scene View Extensions instead.

## Getting Started

Before getting started, there are a few things we ini commands we can add to make debugging our shading model implementation
easier, see [here](/unrealrenderpipeline/shadingmodels/helpfulinicommands/).

Once you've checked that out, head over to [Creating a Shading Model](/unrealrenderpipeline/shadingmodels/creatingshadingmodels/)!

---

### Sources  
> [1] [New shading models and changing the GBuffer by One3y3](https://dev.epicgames.com/community/learning/tutorials/2R5x/unreal-engine-new-shading-models-and-changing-the-gbuffer) dev.epicgames.com.