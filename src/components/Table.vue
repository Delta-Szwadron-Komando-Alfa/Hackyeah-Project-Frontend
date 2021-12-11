<template>
  <div  class="main">
    <Nav @files="upload" />
    <Inside v-if="show" :file="files" />
  </div>
</template>

<script>
import Nav from "./Nav.vue";
import Inside from "./Inside.vue";
export default {
  data: () => ({
    show: true,
    files: [],
  }),
  components: { Nav, Inside },
  methods: {
    upload: function (event) {
      this.files.push(event);
      this.resetChildForm();
    },
    resetChildForm() {
      this.show = false;
      setTimeout(() => {
        this.show = true;
      }, 100);
    },
  },
};
</script>

<style>
.main {
  aspect-ratio: 2/1;
  height: 40vw;
  border-radius: var(--radius);
  display: grid;
  background-color: var(--mainGary);
  grid-template-rows: 10% 60%;
}
</style>
