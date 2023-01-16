<template>
  <div class="wrapper">
    <nav class="menu">
      <a href="" v-for="(navi, i) in navis" :key="i">{{ navi }}</a>
    </nav>
    <div class="list" v-for="(item, i) in items" :key="i">
      <h3>{{ items[i] }}</h3>
      <p>{{ prices[i] }}</p>
      <button @click="report += 1">허위매물신고</button>
      <span>신고수: {{ report }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      report: 0,
      navis: ["Home", "shop", "about"],
      items: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      prices: ["100", "200", "300"],
    };
  },
  components: {},
};
</script>

<style lang="scss">
.list {
  padding: 1rem 0;
}
.menu {
  background: darkslateblue;
  padding: 1rem;
  color: white;
  border-radius: 10px;
  a {
    text-decoration: none;
    color: white;
    padding: 0 10px;
  }
}
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body,
html {
  height: 100%;
  background: #eee;
}
#app {
  height: 100%;
}
.wrapper {
  padding: 1rem;
  background: white;
  margin: 0 auto;
  max-width: 480px;
  height: 100%;
}
</style>
