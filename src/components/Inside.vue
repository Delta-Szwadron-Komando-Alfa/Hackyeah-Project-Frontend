<template>
  <div v-cloak @drop.prevent="addFile" @dragover.prevent>
    <div v-if="files.length < 1" style="display: grid" class="Inside-Main">
      <div style="margin-left: auto; margin-right: auto; margin-top: 30px">
        <img class="arrowsDown" src="../assets/arrowsDown.svg" />
      </div>
      <div style="overflow: hidden" class="inside">Drop files here</div>
    </div>
    <div v-if="files.length >= 1" style="overflow: auto" class="Inside-Main">
      <ListItem v-for="x in files" :key="x" :file="x" @remove="rem" />
    </div>
    <div class=""></div>
  </div>
</template>
<script>
import ListItem from "./ListItem.vue";
export default {
  props: {
    file: Array,
  },
  mounted() {
    for (let i = 0; i < this.file.lenght; i++) {
      this.files.push(this.file[i]);
    }
  },
  components: { ListItem },
  data: () => ({ files: [] }),
  methods: {
    rem(e) {
      //  JSON.parse(JSON.stringify(this.files));
      this.files.splice(this.files.indexOf(e), 1);
      if (this.files.length == 0) {
        let el = document.getElementById("main-big-button");
        el.classList.add("hidden");
      }
    },

    addFile(e) {
      let droppedFiles = e.dataTransfer.files;
      if (!droppedFiles) return;
      [...droppedFiles].forEach((f) => {
        this.files.push(f);
      });
      let el = document.getElementById("main-big-button");
      el.classList.remove("hidden");
    },
  },
};
</script>

<style>
.arrowsDown {
  height: 130%;
}
.inside {
  overflow: scroll;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 3em;
  margin: auto auto auto auto;
}
.Inside-Main {
  margin-left: auto;
  margin-right: auto;
  background-color: var(--mainGary);
  width: 90%;
  height: 140%;
  border-radius: 10px;
  border-color: black;

  /* border-style: dotted; */
}
.cover {
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  position: absolute;
  background-color: rgba(0, 0, 0, 0.637);
  z-index: -1;
}
</style>
