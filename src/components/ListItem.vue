<template>
  <div class="listItem-main">
    <div class="name">{{ files.name }}</div>
    <div
      style="
        margin-left: auto;
        margin-right: 20px;
        margin-top: auto;
        margin-bottom: auto;
      "
    >
      <img
        style="margin-right: 0.7em"
        class="delete"
        @click="generateRaport"
        src="../assets/report.svg"
      />
      <img class="delete" @click="remove" src="../assets/removeCirc.svg" />
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  props: { file: File },
  methods: {
    remove: function () {
      this.$.emit("remove", this.file);
      console.log(this.file);
    },
  },
  mounted() {
    console.log(this.file);
    this.files = this.file;
  },
  data: () => ({
    files: [],
  }),
};
</script>

<style>
.delete {
  height: 2em;
}
.listItem-main {
  padding: 0.125em;
  grid-template-columns: auto auto;
  display: grid;
  margin-top: 15px;
  margin-left: auto;
  margin-right: auto;
  width: 90%;
  height: 55px;
  border-radius: var(--radius);
  background-color: var(--backgorund);
  margin-bottom: auto;
}
.listItem-main:hover {
  background-color: rgb(177, 177, 177);
  transition: background-color 250ms;
}
.name {
  font-size: 2em;
  font-family: Arial, Helvetica, sans-serif;
  margin-left: 10px;
  margin-bottom: auto;
  margin-top: auto;
}
.delete:hover {
  cursor: pointer;
  background-color: rgb(167, 167, 167);
  border-radius: 10px;
}
.delete:active {
  background-color: gray;
}
</style>
