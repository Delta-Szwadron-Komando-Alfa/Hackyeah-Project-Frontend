<template>
  <div class="nav">
    <!-- <div class="addFile">
      <input
        @change="doSomething"
        type="file"
        ref="file"
        id="fileUpload"
        hidden
      />
      <img src="../assets/addFile.svg" @click="chooseFiles()" />
    </div> -->
    <!-- <div class="addFile"><img src="../assets/grid.svg" /></div>
    <div class="addFile"><img src="../assets/list.svg" /></div> -->
  </div>
</template>
<script>
export default {
  data: () => ({
    files: [],
  }),
  components: {},
  methods: {
    chooseFiles: function () {
      document.getElementById("fileUpload").click();
    },
    doSomething: function (e) {
      this.files.push(e.target.files[0]);
      this.$.emit("files", this.files);
    },
  },
};
</script>

<style>
.nav {
  display: flex;
  border-radius: var(--radius) var(--radius) 0px 0px;
  width: 100%;
  height: 0vh;
  background-color: --var(mainGary);
}
.addFile {
  margin-top: auto;
  margin-bottom: auto;
  /* border-radius: 10px;
  margin-left: 10px; */
  background-color: white;
  aspect-ratio: 1/1;
  width: 4.5vh;
}
.addFile:hover {
  cursor: pointer;
  background-color: rgb(180, 180, 180);
}

.addFile:active {
  background-color: white;
}
</style>
