<template>
  <f7-row resizable style="height: 80%; min-height: 50px; border:solid;">
    <f7-col class="demo-col-center-content">
      <div resizable id="threejs-container"></div>
    </f7-col>
  </f7-row>
</template>

<script>
import * as THREE from 'three'

export default {
name: 'homeGridCenterTop',
  data() {
    return {
      cube: null,
      renderer: null,
      scene: null,
      camera: null,
      width: null,
      height: null
    }
  },
  methods: {
    init: function() {
      this.width = document.getElementById("threejs-container").parentNode.parentNode.offsetWidth;
      this.height = document.getElementById("threejs-container").parentNode.parentNode.offsetHeight;
      console.log({ width: this.width, height: this.height });

      this.scene = new THREE.Scene()
      this.camera = new THREE.PerspectiveCamera(
        75,
        this.width / this.height,
        0.1,
        1000
      )

      this.renderer = new THREE.WebGLRenderer()
      this.renderer.setSize(this.width, this.height)
      document.getElementById("threejs-container").appendChild(this.renderer.domElement)

      const geometry = new THREE.BoxGeometry(1, 1, 1)
      const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 })
      this.cube = new THREE.Mesh(geometry, material)
      this.scene.add(this.cube)

      this.camera.position.z = 5
    },
    animate: function() {
      requestAnimationFrame(this.animate)

      this.cube.rotation.x += 0.01
      this.cube.rotation.y += 0.01

      this.renderer.render(this.scene, this.camera)
    }
  },
  mounted() {
    this.init()
    this.animate()
  }
}
</script>