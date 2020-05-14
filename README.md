# chromium-ray-tracing

This patch adds hardware accelerated Ray tracing to WebGPU in Chromium. Both Windows and Linux are supported.

// TODO: add binaries

## Useful links:
 - [RT specification](https://github.com/maierfelix/dawn-ray-tracing/blob/master/RT_SPEC.md)
 - [Dawn RT](https://github.com/maierfelix/dawn-ray-tracing) (Chromium's WebGPU implementation)

## Building

Clone Chromium (revision: *b4332347b130a3c912aa0eba1583cb7db071b1e6*).<br/>

Run:
````
gclient sync
gn gen out/Default --args="is_component_build=false is_debug=false use_dawn=true"
autoninja -C out/Default
````

### On Windows:
After building, download [DXC](https://github.com/microsoft/DirectXShaderCompiler/releases) and place *dxcompiler.dll* and *dxil.dll* along *chrome.exe*.<br/>

Make sure you run Chromium with `chrome.exe --no-sandbox`. If the sandbox is not enabled, Chromium cannot load DXC.

### On Linux:
Make sure you have the latest [Vulkan beta driver](https://developer.nvidia.com/vulkan-driver) installed.

Now you can run Chromium.
