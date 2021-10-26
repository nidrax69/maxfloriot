<template>
  <header class="align-center">
    <router-link class="title" to="/" >Max Floriot</router-link>
    <nav>
      <router-link to="/gallery" class="links">Gallery</router-link>
      <a class="links">About</a>
      <a class="links">Contact</a>
    </nav>
  </header>
</template>

<script>
export default {
    name: "header-site"
}
</script>

<style lang="scss" scoped>
header {
  position: absolute;
  display: flex;
  padding: 4px 16px;
  left: 0;
  right: 0;
  z-index: 9999;
  justify-content: space-between;
  font-family: 'Jost', cursive;
  background-color: white;
  box-shadow: 0 0 4px rgb(61, 61, 61);
}


nav {
  font-size: 20px;
  color: #000;
}

nav a.router-link-active {
  font-weight: 400;
  color: rgb(187, 121, 121);
}

nav a {
  margin-left: 10px;
  margin-right: 10px;
  text-transform: none;
  font-weight: 300;
}

nav a:hover {
  transition: color 70ms ease-in-out;

  color: rgb(187, 121, 121);
}
</style>