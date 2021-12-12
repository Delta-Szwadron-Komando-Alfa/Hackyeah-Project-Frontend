<template>
  <div class="home">
    <div class="title">OTWIERACZ.GOV</div>
    <Table :emit="em" class="center" />
    <div class="spacer"></div>
    <BigButton @submit="emiter" class="center" />
  </div>
</template>
<script>
// @ is an alias to /src
import Table from "@/components/Table.vue";
import BigButton from "@/components/BigButton.vue";
export default {
  name: "Home",
  components: {
    Table,
    BigButton,
  },
  data: () => ({
    em: false,
  }),
  methods: {
    emiter: function (event) {
      this.em = event;
    },
  },
};
</script>

<style>
.title {
  font-family: "Inconsolata", monospace;
  font-weight: bold;
  font-size: 5vw;
  top: 0.5em;
  left: 1em;
  position: absolute;
}
.center {
  margin: auto auto auto auto;
}
.home {
  margin-top: 14vh;
  display: grid;
  margin-bottom: 3vh;
}
</style>
