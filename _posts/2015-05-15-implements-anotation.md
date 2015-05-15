---
layout: blogpost
title: Implementing function from external headers
---
Some use cases require to share some common API. For instance the standard library is one of these. But also if a library needs to delegate some part of its implementation to the user of the library needs to do this. C does not offer a native way for this. The way it is done usually is that some prototype of a function is defined in a header and this is shared between the library and the enduser. In an mbeddr only system interfaces would be used for this. But not all software is written in mbeddr and there are several C libraries out there which should be useable with mbeddr. 

It was already possible to implement such functions in mbeddr in a way that it worked correctly when the binary was linked. To do so the external module that represents the header hat to be imported, the function needed to have the ‘prevent namemangling’ set and the name and parameters had to match the function that was implemented. But at this level of *integration* mbeddr did not know about the fact that this function implements some public interface. Just like in good old plain C. But mbeddr is all about giving benefits to C.

### The mbeddr way

In order to make such an implementation explicit we have added a extension to C that allows this. The natural way to this is by adding an annotation to a function. By simply pressing ‘alt + enter’ on a function signature and select the “Add Implements” item form the intentions menu the editor will allow to specify the function declaration to implement. Afterwards the name, parameters and return type will be synced with the referenced function. The generator will take of generating the appropriated C code so the linker will pick the implementation done in mbeddr.

This feature is included in the new 1.0 RC1 release.

Here is a little demo of it:

![gif perview](/images/implements.gif)
