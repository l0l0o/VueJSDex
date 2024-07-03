<script setup>
defineProps({
  pkmnImage: String,
  pkmnName: String,
  pkmnID: Number,
});
</script>

<template>
  <div class="d-col">
    <div id="card">
      <h5>{{ pkmnID }}</h5>
      <img :src="pkmnImage" alt="" />
    </div>
    <h5>{{ pkmnName }}</h5>
  </div>
</template>

<style scoped>
.d-col {
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: start;
  width: 141px;
  height: 190px;
}
h5 {
  padding-left: 4px;
}
#card {
  width: 141px;
  height: 141px;
  border: 3px solid var(--text-color);
  cursor: pointer;
  position: relative;

  h5 {
    position: absolute;
  }

  img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }
}
</style>
