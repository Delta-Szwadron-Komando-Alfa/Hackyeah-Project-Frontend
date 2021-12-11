<template>
  <Home />
</template>

<script>
import Home from "./views/Home.vue";
export default {
  components: {
    Home,
  },
};
</script>

<style>
:root {
  --radius: 25px;
  --backgorund: rgb(214, 214, 214);
  --mainGary: rgb(194, 194, 194);
  --bigButtonGray: rgb(119, 118, 118);
}
html {
  background-color: var(--backgorund);
}
</style>
