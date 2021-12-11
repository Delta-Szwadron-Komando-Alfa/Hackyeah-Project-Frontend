<template>
  <div class="addFile"><img :src="img" /></div>
</template>

<script>
export default {
  props: {
    img: String,
  },
};
</script>

<style>
.addFile {
  
  margin-top: auto;
  margin-bottom: auto;
  border-radius: 10px;
  margin-left: 10px;
  background-color: white;
  aspect-ratio: 1/1;
  width: 4.5vh;
}
</style>
