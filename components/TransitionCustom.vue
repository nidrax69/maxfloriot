<template>
  <div class="loading">
    <div class="left-layer"></div>
    <div class="left-layer left-layer--2"></div>
    <div class="left-layer left-layer--3"></div>
    <div class="left-layer left-layer--4"></div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
html {
  box-sizing: border-box;
}
*,
*:before,
*:after {
  box-sizing: inherit;
  padding: 0;
}
body {
  height: 100%;
  overflow: hidden;
}

.left-layer {
  position: absolute;
  width: 100%;
  height: 100vh;
  top: auto;
  left: -100%;
  bottom: auto;
  right: auto;
  background: #4d606e;
  transition: all 0.7s cubic-bezier(0.645, 0.045, 0.355, 1);
}
.left-layer.active {
  left: 100%;
}
.left-layer--2 {
  background: #d3d4d8;
  transition-delay: 0.3s;
}
.left-layer--3 {
  background: #d3d4d8;
  transition-delay: 0.12s;
}
.left-layer--4 {
  background: #c06c84;
  transition-delay: 0.08s;
}
</style>