<script setup>
import Item from "./components/Item.vue";
</script>

<script>
import Dados from "./dados/services.json";
export default {
  data() {
    return {
      servicos: null,
    };
  },
  mounted() {
    fetch(
      "https://raw.githubusercontent.com/matheuspython/link-list/master/src/dados/services.json"
    )
      .then((res) => res.json())
      .then((res) => (this.servicos = res))
      .catch(() => (this.servicos = Dados));
  },
};
</script>

<template>
  <div class="logospace">
    <a href="https://vuejs.org/" target="_blank">
      <img
        style="width: 70px"
        src="./assets/vue.svg"
        class="logo vue"
        alt="Vue logo"
      />
    </a>
    <h1 class="title">seja bem vindo!</h1>
    <hr />
    <div class="items">
      <Item v-for="(servico, index) in servicos" :key="index" :item="servico" />
    </div>
  </div>
</template>

<style scoped>
.title{
  text-align: center;
  font-family: sans-serif;
}
.logospace a {
  display: flex;
}
.logo {
  margin: 0 auto;
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
.items {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
