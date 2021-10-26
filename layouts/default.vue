<template>
  <div class="h100">
    <HeaderSite />
    <Social />
    <Nuxt />
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  layoutTransition: {
    name: 'layout',
    mode: 'out-in'
  }
};
</script>

<style lang="scss" scoped>
$t-duration: 1600ms;
$t-delay: 400ms;

.layout-enter-active,
.layout-leave-active {
  transition: opacity 0.5s;
}
.layout-enter,
.layout-leave-active {
  opacity: 0;
}
</style>