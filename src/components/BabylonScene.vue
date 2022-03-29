<template>
  <canvas id="renderCanvas" ref="bjsCanvas"/>
</template>

<script>
import { ref, onMounted } from "@vue/runtime-core";
import { createScene } from "../scenes/MyFirstScene";

export default {
  name: "BabylonScene",
  setup() {
    const bjsCanvas = ref(null);

    onMounted(() => {
      if (bjsCanvas.value) {
        createScene(bjsCanvas.value);
      }
    });

    return {
      bjsCanvas,
    };
  },
};
</script>

<style type="text/css">
  body {
        margin: 0;
        padding: 0;
        width: 100vw;
        height: 100vh;
    }
    #renderCanvas {
        margin: 0;
        padding: 0;
        width: 960px;
        height: 540px;
    }
</style>