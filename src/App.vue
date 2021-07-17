<template>
  <h1>원룸팜</h1>

  <div class="menu">
    <!-- menus의 -->
    <a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
  </div>

  <div class="items" v-for="(item, i) in items" :key="i">
    <h3>{{ items[i].name }}</h3>
    <p>{{ items[i].price }}만원</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    // data 보관함 변수 같은 것들을 여기에 다 보관한다고 보면 된다

    return {
      menus: ["Home", "Products", "About"],
      style: "color:red", // style도 데이터바인딩 가능 대신 : 붙여줘야한다
      items: [
        { name: "양재동원룸", price: 50 },
        { name: "신림동원룸", price: 60 },
        { name: "강호동원룸", price: 70 },
      ],
    };
  },

  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
