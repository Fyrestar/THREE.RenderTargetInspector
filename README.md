![RTI-01](https://user-images.githubusercontent.com/28584767/157973341-1f0d715f-56de-4a4d-a6d8-725d6a5b9a0e.png)

# THREE.RenderTargetInspector

A helper for debugging WebGLRenderTarget. It will add a sidebar overlay that can be placed at left, right, top and bottom, showing live-thumbnails of the inspecting render targets or data textures, by clicking on those they will be opened in a popup you can zoom in and move around, inspect pixel values and positions.

![RTI](/RTI.png)

Click on the small square above each thumbnail to save the render target as PNG.

[Demo: webgl gpgpu water](https://mevedia.com/share/RenderTargetInspector)

```javascript
const rti = new THREE.RenderTargetInspector( renderer, 256, 'left' );
rti.add( renderTarget, 'Some render target' );
rti.add( material.uniforms.dataTexture, 'Data texture from uniform' );
rti.add( material.uniforms.dataTexture.value, 'Data texture' );
rti.add( csm.lights, null, { // An array of lights
	type: 'depth'
});
```

Calling update in your render loop.

```javascript
rti.update()
```
