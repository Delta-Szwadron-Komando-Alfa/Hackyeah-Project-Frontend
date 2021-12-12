<template>
  <div class="cluster">
    <div id="main-big-button" @click="generate" class="main-big-button hidden">
      {{ text }}
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    text: "Submit",
  }),
  methods: {
    generate: function () {
      if (this.text == "Return") {
        this.text = "Submit";
        this.$.emit("submit", false);
      } else {
        this.$.emit("submit", true);
        this.text = "Return";
      }
    },
  },
};
</script>

<style>
.cluster {
  display: grid;
  grid-template-rows: 28% 20%;
}
.hidden {
  opacity: 0;
  z-index: -1;
  transition: 0.5s all;
}
.main-big-button {
  padding: 0.25em;
  text-align: center;
  display: grid;
  font-family: Arial, Helvetica, sans-serif;
  margin-top: 90px;
  font-size: 3em;
  width: 15vw;
  border-radius: 10px;
  background-color: var(--mainGary);
  height: 1.2em;
  transition: 0.5s all;
  min-width: 50vw;
  max-width: 4vh;
  /* border: 1px solid rgb(114, 114, 114); */
  /* box-shadow: 0 1px 2px 0 rgba(0,0,0,0.2), 0 5px 15px 0 rgba(0,0,0,0.19); */
}
.main-big-button:hover {
  background-color: var(--bigButtonGray);
  transition: 0.5s all;
  cursor: pointer;
  color: var(--backgorund);
}
.main-big-button:active {
  border: 1px solid var(--mainGary);
  background-color: var(--mainGary);
  transition: 0.2s all;
}
</style>
