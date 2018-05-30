## three-3dsloader

[THREE.OBJLoader](https://threejs.org/examples/js/loaders/OBJLoader.js) repackaged as a node module

## install

`npm i --save three-obj-mtl-loader`

## usage

```js

var THREE = require('three');
var OBJLoader = require('three-obj-mtl-loader');

import * as THREE from 'three'
import {MTLLoader, OBJLoader} from 'three-obj-mtl-loader'

let scene = new THREE.Scene()

let mtlLoader = new MTLLoader();

let objLoader = new THREE.OBJLoader();

mtlLoader.load('./test.mtl', (materials) => {
  materials.preload()
  objLoader.setMaterials(materials)
  objLoader.load('./test.obj', (object) => {
    scene.add(object)
  })
})

```