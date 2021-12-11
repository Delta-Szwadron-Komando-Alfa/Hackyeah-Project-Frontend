<template>
  <div class="home">
    <Table class="center" />
    <div class="spacer"></div>
    <BigButton class="center" />
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
};
</script>

<style>
.center {
  margin: auto auto auto auto;
}
.home {
  margin-top: 15vh;
  display: grid;
  margin-bottom: 3vh;
}
</style>
