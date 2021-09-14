<template>
  <div id="app">
    <h1>Make your choice!</h1>
    <card-item></card-item>
    <flush></flush>
  </div>
</template>

<script>
import CardItem from "./components/CardItem.vue";
import Flush from "./components/Flush.vue";

export default {
  name: "App",
  components: {
    CardItem,
    Flush,
  },
};
</script>

<style>
body {
  background-color: #ffe8e8;
}
#app {
  font-family: "Helvetica", "Arial", "LiHei Pro", "黑體-繁", "微軟正黑體",
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #3b0000;
  margin-top: 60px;
}
</style>
