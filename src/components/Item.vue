<template>
  <div class="card">
    <a :href="item.href">
      <img :src="item.img" alt="item do serviço" />
    </a>
    <span>
      {{ item.titulo }}
    </span>
  </div>
</template>

<script>
export default {
  props: ["item"],
};
</script>

<style scoped>
div {
  margin: 20px 50px 20px 50px;
  display: block;
  width: 100px;
}
img {
  width: 80px;
}
span {
  font-weight: 900;
}
.card{
    min-width: 120px;
    min-height: 150px;
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    border:1px solid gray;
    border-radius: 5%;
    box-shadow: 0 0 2em gray;
    opacity: 0.9;
    transition: .4s;
}
.card:hover{
      box-shadow: 0 0 4em gray;
    opacity: 1;
}
</style>
