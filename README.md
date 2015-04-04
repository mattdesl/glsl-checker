# glsl-checker

[![stable](http://badges.github.io/stability-badges/dist/stable.svg)](http://github.com/badges/stability-badges)

![img](http://i.imgur.com/NWzvJmm.png)

[(glslb.in demo)](http://glslb.in/s/6fe45d18)

GLSL utility for checkered patterns.

```glsl
uniform vec2 iResolution;

#pragma glslify: checker = require('glsl-checker')

void main() {
  vec2 uv = vec2(gl_FragCoord.xy / iResolution.xy);

  //optionally fix aspect ratio
  uv.x *= iResolution.x / iResolution.y;

  //18x18 checkered background
  float gray = mix(0.8, 1.0, checker(uv, 18.0));
  
  gl_FragColor.rgb = vec3(gray);
  gl_FragColor.a = 1.0;
}
```

## Usage

[![NPM](https://nodei.co/npm/glsl-checker.png)](https://www.npmjs.com/package/glsl-checker)

#### `float c = checker(vec2 uv, float n)`

Creates a checkered `n x n` pattern with the given UV coordinates, returning a float 0.0 or 1.0.

## License

MIT, see [LICENSE.md](http://github.com/mattdesl/glsl-checker/blob/master/LICENSE.md) for details.
