<template>
  <!-- props로 close라는 함수를 넘겨준다 -->

  <h1>원룸팜</h1>

  <div class="menu">
    <!-- menus의 -->
    <a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
  </div>
  <div class="items" v-for="(item, i) in datas" :key="i">
    <img class="image" :src="datas[i].image" @click="modalOpen = true" />
    <h3>{{ datas[i].title }}</h3>
    <p>{{ datas[i].price }}만원</p>
    <p>{{ datas[i].content }}</p>
    <modal
      v-if="modalOpen"
      @close="modalOpen = false"
      :info="this.datas[i]"
    ></modal>

    <!-- 버튼에 코드 달아주기 매우 직관적이다..! -->
    <!-- <button class="btn" @click="items[i].count++" @mouseover="test">
      허위매물 신고
    </button>
    <span>신고수 : {{ items[i].count }}</span> -->
  </div>
</template>

<script>
import oneRooms from "./data";
import modal from "./components/Modal.vue";
console.log("원룸데이터", oneRooms);

export default {
  name: "App",
  data() {
    // data 보관함 변수 같은 것들을 여기에 다 보관한다고 보면 된다

    return {
      datas: oneRooms,
      modalOpen: false,
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

    closeModal() {
      this.modalOpen = false;
    },
  },

  components: { modal },
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

body {
  margin: 0;
}
div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.1);
  position: fixed;
  top: 0;
}

.white-bg {
  margin: 0 auto;
  width: 80%;
  background-color: white;
  border-radius: 8px;
  padding: 20px;
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
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
