# CameraPath

A `Three.js` module for moving a camera along a predefined GLTF path, with optional support for a separate look-at path.

## Installation

```js
import CameraPath from './modules/CameraPath/CameraPath.js'

## Usage

### Configuration

```js
const cameraPathSettings = {

  path: './paths/camera-path.glb',
  lookAtPath: './paths/lookat-path.glb',

  useLookAtPath: true,

  reversePath: false,
  reverseLookAtPath: false,

  positionSmoothing: 0.1,
  rotationSmoothing: 0.0425,

  positionOffset: { x: 0, y: 0, z: 1 },
  rotationOffset: { x: 0, y: 0, z: 0 },

  startSegment: 0,

  debug: {
    log: true,
    visualise: {
      mesh: true,
      steps: true,
      axes: false,
      lookAtSteps: true,
    },
  },

  dracoDecoderPath: './draco/gltf/',

}

### Initialization

```js
const cameraPath = new CameraPath(scene, camera, cameraPathSettings)


### Traversal

```js
cameraPath.traversePath(value, true, false)

- **value**: A number between `0` and `1` representing normalized progress along the path  
- **interpolate** (`true`): Enables position and rotation smoothing  
- **clamp** (`false`): If `false`, allows extrapolation beyond the path bounds  
