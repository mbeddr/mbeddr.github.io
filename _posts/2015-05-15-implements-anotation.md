---
layout: blogpost
title: Implementing function from external headers
---
Some use cases require to share some common API between multiple compilation units. For instance the standard library is one of these. But also if a library needs to delegate some part of its implementation to the user of the library. C does not offer a native way for this. The way it is done usually is that a prototype of a function is defined in a header and this header is shared between the library and the user. In mbeddr only systems interfaces would be used for this. But not all software is written in mbeddr and there are several C libraries out there that use this which we want to be usable with mbeddr. 

It was already possible to implement such functions in mbeddr in a way that it works correctly when the binary is linked. To do so the external module that represents the header has to be imported, the function needs to have the ‘prevent namemangling’ set and the name and parameters have to match the function that was implemented. But at this level of *integration* mbeddr did not know about the fact that this function implements some public interface. Just like in good old plain C.

### The mbeddr way

In order to make such an implementation explicit we have added an extension to C. The natural way to this is by adding an annotation to a function. By simply pressing `alt + enter` on a function signature and select the “Add Implements External Function” item form the intention menu the editor will allow to specify the function declaration to implement. Afterwards the name, parameters and return type will be synced with the referenced function. The generator will take of generating the appropriate C code so the linker will pick the implementation done in mbeddr.

This feature is included in the new 1.0 RC1 release.

Here is a little demo of it:

![gif perview](/images/implements.gif)
