<template>
  <div class="main">
    <Nav @files="upload" />
    <Inside v-if="show" :file="files" />
  </div>
</template>

<script>
import Nav from "./Nav.vue";
import Inside from "./Inside.vue";
import axios from "axios";
export default {
  data: () => ({
    x: true,
    show: true,
    files: [],
  }),
  components: { Nav, Inside },
  props: { emit: Boolean },
  watch: {
    emit: function (val) {
      if (val != !val) {
        axios.post("http://localhost:8000/upload", this.file).then(
          (res) => {
            console.log(res);
          },
          (err) => {
            console.log(err);
          }
        );
      }
    },
  },
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
  height: 33vw;
  border-radius: var(--radius);
  display: grid;
  background-color: var(--mainGary);
  grid-template-rows: 8% 60%;
}
</style>
