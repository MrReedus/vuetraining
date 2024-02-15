<template>
  <div class="container">
    <!-- <div class="img-wrapper">
      <img v-show="isCatVisible" src="../assets/cat.jpg" alt="" /> -->
    <!-- <h1 v-else>Кот скоро вернётся)</h1> -->
    <!-- </div>
    <h2>шаверма кот</h2>
    <div class="controls">
      <button class="btn">сепия</button>
      <button class="btn">рамка</button>
      <button class="btn">уменьшить</button>
      <button @click="isCatVisible = !isCatVisible">Показать\ скрыть</button>
    </div>-->
  </div>
</template>

<script>
export default {
  name: "PhotoRedactor",
  data() {
    return {
      isCatVisible: true,
    };
  },
  methods: {},
};
</script>

<style lang="css" scoped>
.controls {
  display: flex;
  gap: 10px;
}
</style>
