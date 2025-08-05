<template>
  <div id="app">
    <h1>Immersive 3D</h1>
    <div ref="scene" class="scene"></div>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'

export default {
  name: 'App',
  setup() {
    const scene = ref(null)

    onMounted(() => {
      gsap.to(scene.value, { 
        duration: 2, 
        rotation: 360, 
        scale: 1.2, 
        yoyo: true, 
        repeat: -1 
      })
    })

    return {
      scene
    }
  }
}
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  text-align: center;
  margin-top: 60px;
}

.scene {
  width: 200px;
  height: 200px;
  background: linear-gradient(45deg, #667eea 0%, #764ba2 100%);
  margin: 20px auto;
  border-radius: 10px;
}

h1 {
  color: #2c3e50;
}
</style>