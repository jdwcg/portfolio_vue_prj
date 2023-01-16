<template>
  <div class="wrapper">
    <nav class="menu">
      <a href="" v-for="(navi, i) in navis" :key="i">{{ navi }}</a>
    </nav>
    <div class="list" v-for="(item, i) in items" :key="i">
      <h3 @click="modal = true">{{ items[i] }}</h3>
      <p>{{ prices[i] }}</p>
      <button @click="increase(i)">허위매물신고</button>
      <span>신고수: {{ report[i] }}</span>
    </div>
  </div>

  <div class="modal" v-if="modal === true">
    <div class="white_bg">
      <div class="close" @click="modal = false">닫기</div>
      <h4>상세</h4>
      <p>상세내용</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      modal: false,
      report: [0, 1, 2],
      navis: ["Home", "shop", "about"],
      items: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      prices: ["100", "200", "300"],
    };
  },
  components: {},
  methods: {
    increase(i) {
      this.report[i] += 1;
    },
  },
};
</script>

<style lang="scss">
.close {
  position: absolute;
  right: 0;
  top: 0;
  padding: 1rem;
}
.modal {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  top: 0;
  padding: 20px;
}
.white_bg {
  position: relative;
  border-radius: 10px;
  width: 100%;
  height: 300px;
  background: white;
  padding: 20px;
}
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
