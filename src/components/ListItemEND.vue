<template>
  <div class="listItem-main">
    <div class="name">{{ files.name }}</div>
    <div class="claster">
      <div
        style="
          margin-left: auto;
          margin-right: 20px;
          margin-top: auto;
          margin-bottom: auto;
        "
      >
        <img class="delete" @click="download" src="../assets/pdf.svg" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: { file: File },
  component: {},
  methods: {},
  downolad() {},
  mounted() {
    this.files = this.file;
  },
  data: () => ({
    files: [],
  }),
};
</script>

<style>
.claster {
  display: flex;
}
.delete {
  height: 2em;
}
.listItem-main {
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
