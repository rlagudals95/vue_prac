<template>
  <h1>원룸팜</h1>

  <div class="menu">
    <!-- menus의 -->
    <a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
  </div>
  <div class="items" v-for="(item, i) in items" :key="i">
    <img class="image" :src="require(`${items[i].image}`)" />
    <h3>{{ items[i].name }}</h3>
    <p>{{ items[i].price }}만원</p>
    <!-- 버튼에 코드 달아주기 매우 직관적이다..! -->
    <button class="btn" @click="items[i].count++" @mouseover="test">
      허위매물 신고
    </button>
    <span>신고수 : {{ items[i].count }}</span>
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
        {
          name: "양재동원룸",
          price: 50,
          count: 0,
          image: "./assets/room1.png",
        },
        {
          name: "신림동원룸",
          price: 60,
          count: 0,
          image: "./assets/room2.jpg",
        },
        {
          name: "강호동원룸",
          price: 70,
          count: 0,
          image: "./assets/room3.jpg",
        },
      ],
    };
  },

  methods: {
    // 함수는 methods에 선언한다
    increase() {
      // 호출하는 대상의 count를 증가 this를 써주자
      this.count++;
    },
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
  display: flex;
  justify-content: space-evenly;
}

.menu a {
  color: white;
  padding: 10px;
}
.btn {
  margin-right: 1rem;
}

.image {
  width: 100%;
  background-size: cover;
}
</style>
