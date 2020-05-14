# chromium-ray-tracing

This patch adds hardware accelerated Ray tracing to WebGPU in Chromium. Both Windows and Linux are supported.


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

After building, download [DXC](https://github.com/microsoft/DirectXShaderCompiler/releases) and place *dxcompiler.dll* and dxil.dll along *chrome.exe*.<br/>

Now you can run chromium with `chrome.exe --no-sandbox`.
