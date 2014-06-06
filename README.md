# glsl-luma [![stable](http://badges.github.io/stability-badges/dist/stable.svg)](http://github.com/badges/stability-badges)

Get the luma (brightness) of an RGB color in GLSL. Useful for converting images to greyscale.

[![glsl-luma](http://imgur.com/7O5SbmC)](http://hughsk.io/glsl-luma)

## Usage

[![NPM](https://nodei.co/npm/glsl-luma.png)](https://nodei.co/npm/glsl-luma/)

### `float value = luma(vec3 rgb)`
### `float value = luma(vec4 rgba)`

Takes a `vec3` or `vec4` color as input, returning the luma as a `float`.

``` glsl
precision mediump float;

uniform sampler2D uTexture;
varying vec2 vUv;

#pragma glslify: luma = require(glsl-luma)

void main() {
  vec4 color = texture2D(uTexture, vUv);
  float brightness = luma(color);

  gl_FragColor = vec4(vec3(brightness), 1.0);
}
```

## License

MIT. See [LICENSE.md](http://github.com/hughsk/glsl-luma/blob/master/LICENSE.md) for details.
