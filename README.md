# SwiftShader

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

Original SwiftShader repository
------------

SwiftShader is a high-performance CPU-based implementation of the Vulkan 1.3 graphics API.

Original repository - https://github.com/google/swiftshader

SwiftShader Fork with `gl_PrimitiveID` Support
------------

The original SwiftShader repository does **not** implement geometry shaders and does **not** support `gl_PrimitiveID` in fragment shaders.  
If you try to use `gl_PrimitiveID` in a fragment shader on upstream SwiftShader, you will encounter:

- A warning: ```WARNING: UNSUPPORTED: Unsupported capability 2```
- Incorrect behavior: values of `gl_PrimitiveID` in fragment shaders are essentially random.

Changes in this fork
------------

- Removed the capability warning when `gl_PrimitiveID` is used
- Implemented proper support for passing the correct primitive index to fragment shaders

This makes it possible to safely use `gl_PrimitiveID` in fragment shaders.
